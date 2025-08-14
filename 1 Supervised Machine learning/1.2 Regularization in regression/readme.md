# Regularization in Regression

Regularization is introduced to control over-fitting because the model learns or fits the training data **too well**, including noise or irrelevant patterns. As a result, it performs poorly on new (unseen) data.

## Types of Regularization

The types of regularization technique discussed here include:

- **Ridge Regression**
- **Lasso Regression**
- **Elastic Net**

There can be more types, and you can choose based on your specific requirements.

---

## Bias-Variance Indicators

- **High Bias (Underfitting):**  
  Jₜᵣₐᵢₙ is high,  
  J꜀ᵥ is high
  


- **High Variance (Overfitting):**  
   Jₜᵣₐᵢₙ is low,  
   J꜀ᵥ is high

---

## Purpose of Regularization
To prevent overfitting, we introduce a **penalty term** in the cost function so that the model performs better on new data. This penalty discourages the model from assigning **large weights** to coefficient terms, helping generalize the model.

--- 

📂 Resources and References
📊 Dataset

Name: [California_housing ](https://www.kaggle.com/datasets/mks2192/california-housing)

Source: Kaggle


🖼️ External Images Used

Image 1: [/regularization.png](https://miro.medium.com/v2/resize:fit:1100/format:webp/0*-aJ9MXozOKv6joiX.png)

📄 Materials and Documentation

TensorFlow Documentation: https://www.tensorflow.org/api_docs

Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow — Chapter 4, Training Models

An Introduction to Statistical Learning — Chapter 6, Linear Model Selection and Regularization


🙏 Acknowledgements

Kaggle community for the dataset.

TensorFlow team for the machine learning framework.

Authors of the books metioned.

Matplotlib developers for visualization tools.