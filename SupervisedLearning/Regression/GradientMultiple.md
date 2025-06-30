# Multiple Linear Regression: Gradient Descent & Vectorization

## Overview

Multiple Linear Regression models the relationship between input features **x** and a continuous target **y** using parameters **w** (weights) and **b** (bias).

---

### Vectorized Formulation

- **Prediction:**  
  \[
  \hat{y} = w^\top x + b
  \]
  where \( w \in \mathbb{R}^n \), \( x \in \mathbb{R}^n \), \( b \in \mathbb{R} \).

- **Cost Function:**  
  For \( m \) training examples:
  \[
  J(w, b) = \frac{1}{2m} \sum\_{i=1}^m \left( w^\top x^{(i)} + b - y^{(i)} \right)^2
  \]

---

### Gradient Descent Updates

To minimize \( J(w, b) \), update parameters as:

- **Weights:**  
  \[
  w := w - \alpha \frac{\partial J(w, b)}{\partial w}
  \]
- **Bias:**  
  \[
  b := b - \alpha \frac{\partial J(w, b)}{\partial b}
  \]

Where \( \alpha \) is the learning rate.

**Gradients:**

- **Weights:**
  \[
  \frac{\partial J(w, b)}{\partial w} = \frac{1}{m} \sum\_{i=1}^m \left( w^\top x^{(i)} + b - y^{(i)} \right) x^{(i)}
  \]
- **Bias:**
  \[
  \frac{\partial J(w, b)}{\partial b} = \frac{1}{m} \sum\_{i=1}^m \left( w^\top x^{(i)} + b - y^{(i)} \right)
  \]

Repeat updates until convergence.

---

## Why Vectorization?

- **Faster computation** (batch operations)
- **Cleaner, more efficient code**
- **Alignment with ML frameworks** (e.g., NumPy, PyTorch)

---

## Normal Equation (Closed-form Solution)

An alternative to gradient descent:

- **Analytical solution:**  
  For data matrix \( X \in \mathbb{R}^{m \times n} \), target \( y \in \mathbb{R}^m \):
  \[
  w = (X^\top X)^{-1} X^\top y
  \]
- **No iterations needed**
- **Not suitable** for very large datasets or non-linear models

---

## Implementation Tips

- Use NumPy for all matrix and vector operations.
- Implement model, cost, and gradients using vectorized code.
- Prefer gradient descent for large or complex datasets.

---

## Summary

Multiple Linear Regression is foundational in ML. Efficient implementation with vectorization and gradient descent is essential for scalable machine learning.
