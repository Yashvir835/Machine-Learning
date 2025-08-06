## Elastic Net Regression

This document provides a clear and comprehensive explanation of Elastic Net Regression, which combines both L1 and L2 regularization to balance feature selection and coefficient shrinkage.

## Table of Contents

1. [Introduction](#introduction)
2. [The Core Concepts](#the-core-concepts)

   * [Key Concepts](#key-concepts)
   * [Advantages of Elastic Net](#advantages-of-elastic-net)
   * [Disadvantages of Elastic Net](#disadvantages-of-elastic-net)
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

Elastic Net Regression is a linear model that incorporates both L1 and L2 regularization. It is especially useful when there are multiple correlated features, providing a middle ground between Lasso and Ridge.

## The Core Concepts

### Key Concepts

1. **Elastic Net** is a middle ground between Ridge and Lasso regression.
2. Regularization helps control **overfitting** and handles **multicollinearity**.
3. Mix ratio **α** controls interpolation:

   * **α = 0** → equivalent to Ridge Regression.
   * **α = 1** → equivalent to Lasso Regression.

### Advantages of Elastic Net

* Performs **variable selection** with grouping — sets some coefficients exactly to zero and selects correlated features together.
* Balances **sparsity** and **shrinkage** by tuning **α**.
* Effective when **multiple related features** influence the response.

### Disadvantages of Elastic Net

* When **α < 1**, coefficients are shrunk rather than dropped entirely, so models may remain somewhat dense.

## Cost Function

The regularized cost function in Elastic Net Regression is:

```text
J(θ) = MSE(θ) + α Σⁿᵢ=₁ |θᵢ| + (1 - α) Σⁿ ᵢ=₁θᵢ²
```

Where:

* `MSE(θ)` is the mean squared error term.
* `α` ∈ \[0,1] controls the balance between L1 and L2 penalties.
* `θᵢ` is the parameter for feature `i`.

Here, the hypothesis function is:

```text
f_θ(x) = θ₀ + Σⁿᵢ=₁ θᵢ xᵢ
```

## Regularization Term

This consists of both L1 and L2 norms:

```text
Regularization Term = α Σⁿᵢ=₁ |θᵢ| + (1 - α) Σⁿᵢ=₁ θᵢ²
```

## Mathematical Intuition
![Ridge Plot](../regularization.png)

Elastic Net adds constraints on both the L1 and L2 norms of the parameter vector `θ`:

```text
Σⁿᵢ=₁ |θᵢ| ≤ t₁  and  Σⁿᵢ=₁ θᵢ² ≤ t₂
```

By adjusting **α**, we move between the **diamond-shaped** region (L1) and the **circular** region (L2).

## Visual Intuition: Loss Surface & Constraint

* The **squared loss** `(yᵢ - ŷᵢ)²` forms **elliptical contours** in `θ`-space.
* The **constraint region** is a blend of **diamond** (L1) and **circle** (L2).

**Optimization Interpretation:**

1. Slide the elliptical contours toward the blended constraint region.
2. The first contact point gives the optimal `θ`, combining sparsity and shrinkage.

## Summary

* Elastic Net provides a flexible approach by **combining** L1 and L2 penalties.
* **α** lets you interpolate between **pure shrinkage** (Ridge) and **pure sparsity** (Lasso).
* Particularly effective for **correlated features** and high-dimensional data.

## How to Use This Repository

This repository is primarily for educational purposes.

* **Read this `README.md` file** to understand theoretical concepts.
* **Explore the Jupyter Notebook** (`elastic_net_demo.ipynb`) for a practical implementation.
* **Check the code in the `/src` directory** for a modularized implementation.

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
