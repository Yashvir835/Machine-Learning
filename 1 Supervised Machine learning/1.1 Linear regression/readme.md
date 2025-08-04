# Understanding Linear Regression

This repository is dedicated to providing a clear and comprehensive explanation of Linear Regression, one of the most fundamental algorithms in statistics and machine learning.

## Table of Contents
1.  [Introduction](#introduction)
2.  [The Core Concepts](#the-core-concepts)
    * [The Hypothesis Function](#the-hypothesis-function)
    * [The Cost Function](#the-cost-function)
    * [The Goal: Minimizing Cost](#the-goal-minimizing-cost)
3.  [Optimization with Gradient Descent](#optimization-with-gradient-descent)
    * [Intuition](#intuition)
    * [The Algorithm](#the-algorithm)
    * [The Learning Rate ($\alpha$)](#the-learning-rate-alpha)
4.  [Assumptions of Linear Regression](#assumptions-of-linear-regression)
5.  [Evaluating the Model](#evaluating-the-model)
6.  [How to Use This Repository](#how-to-use-this-repository)
7.  [Contributing](#contributing)
8.  [License](#license)

## Introduction

Linear Regression is a supervised learning algorithm used to model the linear relationship between a dependent variable (the output or target) and one or more independent variables (the inputs or features). The goal is to find the best-fitting straight line (or hyperplane in higher dimensions) that describes the data.

It's a foundational algorithm for anyone starting in data science or machine learning due to its simplicity and interpretability.

## The Core Concepts

To understand linear regression, we need to understand three key components: the hypothesis function, the cost function, and the optimization method used to minimize the cost.

### The Hypothesis Function

The hypothesis function, denoted as $h_\theta(x)$, is the function that our model uses to make predictions.

**1. Simple Linear Regression (One Feature)**

For a single feature $x$, the hypothesis is the equation of a straight line:
$$h_\theta(x) = \theta_0 + \theta_1 x$$
* $\theta_0$ is the intercept (the value of $y$ when $x=0$).
* $\theta_1$ is the coefficient or slope (the change in $y$ for a one-unit change in $x$).

**2. Multiple Linear Regression (Multiple Features)**

When we have multiple features ($x_1, x_2, \dots, x_n$), the function becomes:
$$h_\theta(x) = \theta_0 + \theta_1 x_1 + \theta_2 x_2 + \dots + \theta_n x_n$$
* Here, $\theta_0$ is the intercept, and $\theta_1, \dots, \theta_n$ are the coefficients for each corresponding feature.

### The Cost Function

How do we know if our hypothesis function is good? We measure its performance using a **cost function** (or loss function). The cost function calculates the error, or the difference between the predicted values ($\hat{y} = h_\theta(x)$) and the actual values ($y$).

For linear regression, the most common cost function is the **Mean Squared Error (MSE)**, often denoted as $J(\theta)$.

$$J(\theta) = \frac{1}{2m} \sum_{i=1}^{m} (h_\theta(x^{(i)}) - y^{(i)})^2$$

Where:
* $m$ is the number of training examples.
* $x^{(i)}$ is the feature vector for the $i$-th training example.
* $y^{(i)}$ is the actual target value for the $i$-th training example.
* $h_\theta(x^{(i)})$ is the model's prediction for the $i$-th example.
* The $\frac{1}{2}$ is a convention used to simplify the derivative calculation during optimization.

### The Goal: Minimizing Cost

The goal of "training" the model is to find the optimal values for the parameters ($\theta_0, \theta_1, \dots, \theta_n$) that **minimize the cost function $J(\theta)$**. In other words, we want to find the line that is, on average, closest to all the data points.

## Optimization with Gradient Descent

Gradient Descent is an iterative optimization algorithm used to find the minimum of a function. We use it to find the values of $\theta$ that minimize our cost function $J(\theta)$.

### Intuition

Imagine you are standing on a hill and want to get to the lowest point. You would look around you and take a step in the direction that goes downhill most steeply. You repeat this process until you can't go any lower. Gradient Descent does exactly this for our cost function.

### The Algorithm

The algorithm repeatedly updates each parameter $\theta_j$ by taking a small step in the direction of the negative gradient of the cost function. The update rule is:

$$\theta_j := \theta_j - \alpha \frac{\partial}{\partial \theta_j} J(\theta)$$

Let's break this down:
* $\theta_j$ is the parameter we are updating.
* $:=$ is the assignment operator.
* $\alpha$ is the **learning rate**, which controls the size of the step we take.
* $\frac{\partial}{\partial \theta_j} J(\theta)$ is the partial derivative of the cost function with respect to $\theta_j$ (the direction of the steepest ascent).

For our MSE cost function, the derivative term calculates to:
$$\frac{\partial}{\partial \theta_j} J(\theta) = \frac{1}{m} \sum_{i=1}^{m} (h_\theta(x^{(i)}) - y^{(i)})x_j^{(i)}$$

So, we simultaneously update all $\theta_j$ in each iteration until the algorithm converges to a minimum.

### The Learning Rate ($\alpha$)

The learning rate is a critical hyperparameter:
* **If $\alpha$ is too small:** Gradient descent will be very slow to converge.
* **If $\alpha$ is too large:** The algorithm might overshoot the minimum and fail to converge, or even diverge.

## Assumptions of Linear Regression

For the model's results to be reliable and interpretable, several assumptions about the data should hold:

1.  **Linearity:** The relationship between the features and the target is linear.
2.  **Independence:** The observations (and their errors) are independent of one another.
3.  **Homoscedasticity:** The errors have constant variance at every level of the features.
4.  **Normality of Residuals:** The errors (residuals) of the model are normally distributed.
5.  **No Multicollinearity:** The independent features are not highly correlated with each other.

## Evaluating the Model

After training, we evaluate the model's performance on unseen test data using metrics like:

1.  **Mean Absolute Error (MAE):** The average of the absolute errors.
    $$MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|$$

2.  **Mean Squared Error (MSE):** The average of the squared errors.
    $$MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$$

3.  **R-squared ($R^2$) Score:** The proportion of the variance in the target that is predictable from the features. An $R^2$ of 1 indicates a perfect fit.
    $$R^2 = 1 - \frac{\sum_{i=1}^{n} (y_i - \hat{y}_i)^2}{\sum_{i=1}^{n} (y_i - \bar{y})^2}$$

## How to Use This Repository

This repository is primarily for educational purposes.
* **Read this `README.md` file** to understand the theoretical concepts.
* **Explore the Jupyter Notebook (`linear_regression_demo.ipynb`)** for a practical, hands-on implementation of these concepts in Python.
* **Check the code in the `/src` directory** for a modularized version of the implementation.

## Contributing

Contributions are welcome! If you find any errors, typos, or have suggestions for improvement, please feel free to:
1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-feature-name`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add some feature'`).
5.  Push to the branch (`git push origin feature/your-feature-name`).
6.  Open a Pull Request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
