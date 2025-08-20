## Ridge Regression

This document provides a clear and comprehensive explanation of Ridge Regression (Tikhonov Regularization), a robust regularization technique in statistics and machine learning.

## Table of Contents

1. [Introduction](#introduction)
2. [The Core Concepts](#the-core-concepts)

   * [Key Concepts](#key-concepts)
   * [Advantages of Ridge Regression](#advantages-of-ridge-regression)
   * [Disadvantages of Ridge Regression](#disadvantages-of-ridge-regression)
3. [Cost Function](#cost-function)
4. [Regularization Term](#regularization-term)
5. [Mathematical Intuition](#mathematical-intuition)
6. [Visual Intuition: Loss Surface & Constraint](#visual-intuition-loss-surface--constraint)
7. [Summary](#summary)
8. [How to Use This Repository](#how-to-use-this-repository)
9. [Contributing](#contributing)
10. [License](#license)

---

## Introduction

Ridge Regression (also known as Tikhonov Regularization) is a linear model that incorporates L2 regularization. It is widely used to enhance model stability and mitigate multicollinearity.

## The Core Concepts

### Key Concepts

1. **Ridge Regression** (Tikhonov Regularization)
2. The penalty term is applied **only during training**, not during testing or validation.
3. Regularization helps in:

   * Controlling **overfitting** (high variance)
   * Handling **multicollinearity** — when predictor variables are highly correlated.

### Advantages of Ridge Regression

* Handles **overfitting** by penalizing large parameters.
* Addresses **multicollinearity** effectively.
* Retains all variables, useful when every feature carries information.

### Disadvantages of Ridge Regression

* **Does not perform feature selection** — all features remain in the model.
* Can introduce **bias** by shrinking parameter values toward zero.

## Cost Function

The regularized cost function in Ridge Regression is:

```text
J(θ) = (1 / 2m) * Σᵐᵢ=₁ [f_θ(x⁽ⁱ⁾) - y⁽ⁱ⁾]² + (λ / 2m) * Σⁿⱼ=₁ θⱼ²
```

Where:

* `m`: Number of training examples
* `n`: Number of features (parameters)
* `λ` (or `α`): Regularization parameter
* `θ₀`: Intercept term
* `θⱼ`: Parameter for feature `j`

Here, the hypothesis function is:

```text
f_θ(x) = θ₀ + Σⁿⱼ=₁ θⱼ xⱼ
```

## Regularization Term

This is equivalent to the **squared L2 norm**:

```text
Regularization Term = (λ / 2m) * ||θ||² = (λ / 2m) * Σⁿⱼ=₁ θⱼ²
```

## Mathematical Intuition

Ridge Regression adds a constraint on the size of the parameter vector `θ`:

```text
Σⁿⱼ=₁ θⱼ² ≤ t
```

**Geometrically:**
![Ridge Plot](../regularization.png)

* In 2D:

  ```text
  θ₁² + θ₂² ≤ t
  ```

* In higher dimensions, this becomes a **hypersphere**.

* The threshold `t` relates to `λ`:
  **Larger λ → smaller t → stronger regularization**

## Visual Intuition: Loss Surface & Constraint

* The **squared loss** `(yᵢ - ŷᵢ)²` forms **elliptical contour curves** in `θ`-space (parameter space).
* The **regularization constraint** `||θ||² ≤ t` defines a **circular region** centered at the origin.

**Optimization Interpretation:**

1. Imagine sliding the ellipse (loss contour) toward the origin to minimize the loss.
2. The **moment this ellipse first touches the constraint region**, that point is the **optimal `θ`**.

## Summary

* Ridge Regression is ideal when retaining all features but mitigating overfitting.
* It **shrinks coefficients** without eliminating them.
* Particularly useful for high-dimensional data and multicollinearity.

## How to Use This Repository

This repository is primarily for educational purposes.

* **Read this `README.md` file** to understand theoretical concepts.
* **Explore the Jupyter Notebook** (`ridge_regression_demo.ipynb`) for a practical implementation.

## Contributing

Contributions are welcome! If you find any errors, typos, or have suggestions for improvement, please:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature-name`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin feature/your-feature-name`).
6. Open a Pull Request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
