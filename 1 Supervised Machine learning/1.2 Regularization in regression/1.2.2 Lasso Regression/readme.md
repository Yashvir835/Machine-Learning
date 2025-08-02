# 📘 Lasso Regression

---

## 📌 Key Concepts

1. **Lasso Regression**  
   - Full form: **Least Absolute Shrinkage and Selection Operator Regression**
   - Uses the **L1 norm** of the weight vector as the penalty.
   - Regularization constraint is **diamond-shaped** (in 2D).
   - Encourages **sparsity** — setting some weights exactly to zero.

---

## ✅ Advantages of Lasso Regression

- Performs **feature selection** automatically.
- Produces a **sparse model** — only important variables remain.
- Reduces **overfitting** effectively.
- Works well when **few variables are truly relevant**.

---

## ❌ Disadvantages of Lasso Regression

- Introduces **bias** by shrinking coefficients.
- When features are **correlated**, Lasso tends to:
  - Pick **only one feature** from the group.
  - Randomly **ignore the others**, leading to instability.
- Not suitable when:
  - **All features are important**
  - **Group selection** is desired

---

## 🧮 Cost Function

The regularized cost function in Lasso Regression is:

```text
J(w, b) = (1 / 2m) * Σᵐᵢ=₁ [f₍w,b₎(x⁽ⁱ⁾) - y⁽ⁱ⁾]² + (λ / 2m) * Σⁿⱼ=₁ |wⱼ|
```

Where:
- `m`: Number of training examples  
- `n`: Number of features (coefficients)  
- `λ`: Regularization parameter  
- `wⱼ`: Weight/parameter for feature `j`

---

## 📏 Regularization Term

This is equivalent to the **L1 norm**:

```text
Regularization Term = (λ / 2m) * ||w||₁ = (λ / 2m) * Σⁿⱼ=₁ |wⱼ|
```

---

## 🔍 Mathematical Intuition
![Ridge Plot](../lasso_ridge.jpg)

Lasso Regression adds a constraint on the size of the weight vector `w`:

```text
Σⁿⱼ=₁ |wⱼ| ≤ t
```

### Geometrically:

- In 2D:

  ```text
  |w₁| + |w₂| ≤ t
  ```

- In higher dimensions, this becomes a **cross-polytope**.

- The threshold `t` is a function of `λ`:  
  **Larger λ → smaller t → stronger regularization**

---

## 🧭 Visual Intuition: Loss Surface & Constraint

- The **squared loss** `(yᵢ - ŷᵢ)²` forms **elliptical contour curves** in `w`-space (weight space).
- The **regularization constraint** `||w||₁ ≤ t` defines a **diamond-shaped region** centered at the origin.

**Optimization Interpretation:**

1. Imagine sliding the ellipse (loss contour) toward the origin to minimize the loss.
2. The **first point of contact** between the ellipse and the constraint region is the **optimal `w`**.
3. Since the diamond has sharp corners, the ellipses often touch at these **corners**, resulting in **exact zeros in some `wⱼ`**.

```text
⇒ Sparse solution
```

---

## 📝 Summary

- Lasso regression is ideal when we want a **simplified model** with **automatic feature elimination**.
- It **shrinks coefficients**, often to **exact zero** for some features.
- Useful when **only a few features are important**.
- For correlated or grouped features, consider using **Elastic Net** instead.

---

