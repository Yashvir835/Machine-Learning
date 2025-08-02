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