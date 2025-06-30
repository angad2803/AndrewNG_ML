# 📘 Regularization in Machine Learning — Summary

Regularization is a technique used to reduce **overfitting** in machine learning models by penalizing large weights.

---

## 🔑 Key Concepts

### 1. **Problem of Overfitting**

- High-degree polynomials (e.g. x³, x⁴) can fit training data too well (wiggly curves).
- These models perform poorly on new/unseen data (poor generalization).

---

### 2. **Solution: Regularization**

- Shrinks large weight values **w₁ to wₙ** toward zero.
- Simpler models generalize better.
- Keeps all features, unlike feature selection.

---

### 3. **Modified Cost Function**

#### Original (Linear Regression):

\[
J(w, b) = \frac{1}{2m} \sum (f(x^{(i)}) - y^{(i)})^2
\]

#### Regularized:

\[
J*{reg}(w, b) = \frac{1}{2m} \sum (f(x^{(i)}) - y^{(i)})^2 + \frac{\lambda}{2m} \sum*{j=1}^{n} w_j^2
\]

- The second term is the **regularization term**.
- \(\lambda\) (lambda) is the **regularization parameter**.

---

### 4. **Effect of Lambda (λ)**

| λ Value   | Effect                                     |
| --------- | ------------------------------------------ |
| λ = 0     | No regularization → Overfitting            |
| λ → ∞     | Very strong regularization → Underfitting  |
| Optimal λ | Balance between underfitting & overfitting |

---

### 5. **Practical Notes**

- Usually **do not regularize** the bias term (b).
- Regularization is commonly used in **linear**, **logistic**, and **neural networks**.
- Helps maintain all features, but limits their influence.

---

## ✅ Summary

Regularization helps prevent overfitting by penalizing large weights through an extra term in the cost function. Choosing a good λ is key to balancing model complexity and generalization.

# 🧠 Regularized Linear Regression: Gradient Descent

## 📘 Cost Function (with Regularization)

```
J(w, b) = (1/2m) * Σ [f(xᶦ) - yᶦ]² + (λ/2m) * Σ [wⱼ²]
```

- First term: Squared error (fit to data)
- Second term: Regularization (shrinks parameters)
- λ (lambda): Regularization parameter
- m: Number of training examples

---

## 🔁 Gradient Descent Updates (Regularized)

### For wⱼ (j = 1 to n)

```
wⱼ := wⱼ - α * [ (1/m) * Σ(f(xᶦ) - yᶦ) * xⱼᶦ + (λ/m) * wⱼ ]
```

### For b (not regularized)

```
b := b - α * (1/m) * Σ(f(xᶦ) - yᶦ)
```

---

## 🔍 Interpretation

- Regularization adds `+ (λ/m) * wⱼ` to the gradient.
- Update rule becomes:

```
wⱼ := wⱼ * (1 - αλ/m) - α * usual_gradient
```

→ This shrinks `wⱼ` slightly every iteration.

---

## 💡 Why It Works

- Penalizing large weights reduces overfitting.
- Keeps model simpler → better generalization.
- λ too large → underfitting  
  λ = 0 → overfitting  
  Choose **just right** via validation.

---

## 🧮 Optional Derivative Breakdown

```
∂J/∂wⱼ = (1/m) * Σ[(f(xᶦ) - yᶦ) * xⱼᶦ] + (λ/m) * wⱼ
```

---

## ✅ Summary

- Regularization shrinks `wⱼ` on each iteration.
- Prevents overfitting in models with many features.
- Small change to gradient descent → big improvement.

# Regularized Logistic Regression Summary

## 🎯 Goal

Implement logistic regression with **regularization** to prevent **overfitting**, especially when working with high-order polynomial features or many input features.

---

## 🧠 Background

Just like linear regression, logistic regression can **overfit** if trained on a complex model with many features. Regularization helps prevent this by **penalizing large weights (w)**.

---

## 📉 Cost Function with Regularization

### Original Cost Function (Logistic Regression):

$$
J(w, b) = -\frac{1}{m} \sum_{i=1}^{m} \left[ y^{(i)} \log(f^{(i)}) + (1 - y^{(i)}) \log(1 - f^{(i)}) \right]
$$

where \( f^{(i)} = \sigma(z^{(i)}) = \sigma(w^T x^{(i)} + b) \)

### Regularized Cost Function:

$$
J(w, b) = -\frac{1}{m} \sum_{i=1}^{m} \left[ y^{(i)} \log(f^{(i)}) + (1 - y^{(i)}) \log(1 - f^{(i)}) \right] + \frac{\lambda}{2m} \sum_{j=1}^{n} w_j^2
$$

- \( \lambda \): Regularization parameter.
- Note: **Only w is regularized**, not b.

---

## 🔁 Gradient Descent Update Rules

### Derivatives with Regularization:

- For \( j = 1 \) to \( n \):

$$
\frac{\partial J}{\partial w_j} = \frac{1}{m} \sum_{i=1}^{m} (f^{(i)} - y^{(i)}) x_j^{(i)} + \frac{\lambda}{m} w_j
$$

- For \( b \) (no regularization):

$$
\frac{\partial J}{\partial b} = \frac{1}{m} \sum_{i=1}^{m} (f^{(i)} - y^{(i)})
$$

### Gradient Descent Algorithm:

```python
# Regularized Logistic Regression (gradient descent)
for j in range(n):
    w[j] = w[j] - alpha * ( (1/m) * sum((f[i] - y[i]) * x[i][j] for i in range(m)) + (lambda_/m) * w[j] )

b = b - alpha * (1/m) * sum(f[i] - y[i] for i in range(m))
```

---

## ✅ Result

Regularization prevents large weights \( w_j \), reducing model complexity, and avoids overfitting — especially useful for logistic regression with many features.

---

## 🧪 Tip

Try this in the lab:

- Enable regularization.
- Adjust \( \lambda \) and observe decision boundaries.

---

## 🚀 Coming Next

In the next course, you'll build **neural networks**, leveraging what you've learned (cost functions, gradient descent, sigmoid) to solve more complex tasks like:

- Image recognition
- Self-driving cars
- Speech processing

---

🎉 **Great job finishing Course 1!**
