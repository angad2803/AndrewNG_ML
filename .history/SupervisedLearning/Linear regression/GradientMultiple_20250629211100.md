# Multiple Linear Regression with Gradient Descent and Vectorization

## Overview

Multiple Linear Regression models the relationship between input features **x** and a continuous target **y** using parameters **w** (weights) and **b** (bias).

### Vectorized Form

Instead of treating weights individually (**w₁, w₂, ..., wₙ**), we use a weight vector **w**:

- **Prediction**:  
  \[
  \hat{y} = f\_{w,b}(x) = w^\top x + b
  \]
  where \( w \in \mathbb{R}^n \), \( x \in \mathbb{R}^n \), and \( b \in \mathbb{R} \).

- **Cost Function**:  
  For \( m \) training examples:
  \[
  J(w, b) = \frac{1}{2m} \sum\_{i=1}^m \left( w^\top x^{(i)} + b - y^{(i)} \right)^2
  \]

### Gradient Descent

To minimize the cost function \( J(w, b) \), we use the following updates:

- For weights:  
  \[
  w := w - \alpha \frac{\partial J(w, b)}{\partial w}
  \]
- For bias:  
  \[
  b := b - \alpha \frac{\partial J(w, b)}{\partial b}
  \]

Where \( \alpha \) is the learning rate.

The gradients are:

- For weights:
  \[
  \frac{\partial J(w, b)}{\partial w} = \frac{1}{m} \sum\_{i=1}^m \left( w^\top x^{(i)} + b - y^{(i)} \right) x^{(i)}
  \]
- For bias:
  \[
  \frac{\partial J(w, b)}{\partial b} = \frac{1}{m} \sum\_{i=1}^m \left( w^\top x^{(i)} + b - y^{(i)} \right)
  \]

These updates are repeated until convergence.

## Vectorization Benefits

Using vector operations (NumPy) allows for:

- Faster computation (batch operations)
- Cleaner and more efficient code
- Alignment with advanced ML frameworks

## Normal Equation (Alternative Method)

An alternative to gradient descent is the **Normal Equation**:

- Solves for \( w \) and \( b \) analytically without iterations.
- For data matrix \( X \in \mathbb{R}^{m \times n} \) and target vector \( y \in \mathbb{R}^m \):
  \[
  w = (X^\top X)^{-1} X^\top y
  \]
- **Not** generalizable to algorithms like logistic regression or neural networks.
- Slower with large feature sets.
- May be used internally in libraries like `scikit-learn`.

## Implementation Notes

- Use NumPy for matrix operations and vectorized code.
- The model, cost computation, and gradient descent updates can all be implemented efficiently using vector math.
- Gradient descent is the preferred method in practice due to flexibility and scalability.

## Key Takeaway

Multiple Linear Regression is one of the most widely used algorithms. Learning to implement it efficiently with gradient descent and vectorization is foundational for progressing in ML.

---
