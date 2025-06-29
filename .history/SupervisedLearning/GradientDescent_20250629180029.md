# 🧠 Gradient Descent: Intuition & Overview

## 🧩 Goal:

Minimize the cost function **J(w, b)** to find the best parameters for your model.

---

## 🚶 What is Gradient Descent?

- Gradient Descent is an algorithm to **minimize any function**, including cost functions for:
  - Linear Regression
  - Neural Networks (Deep Learning)
  - Any model with multiple parameters

---

## 🛠️ How It Works:

1. **Start** with initial guesses (often w = 0, b = 0).
2. **Iteratively update** w and b to reduce J(w, b).
3. At each step:
   - Look around your current position (parameter values)
   - Move in the direction of **steepest descent**
   - Take **small steps** (called learning rate steps)

---

## 🏔️ Analogy:

- Imagine standing on a **hilly surface (3D cost plot)**.
- You're trying to reach the **lowest valley** (minimum of cost function).
- You take baby steps **downhill** repeatedly until you reach a valley.
- Depending on your starting point, you may end up in **different valleys** (local minima).

---

## 🔁 Key Concepts:

- Gradient descent can **converge to local minima** depending on start point.
- For **linear regression**, cost surface is a smooth **bowl shape**, so the global minimum is reachable.
- For **neural networks**, cost surfaces are more complex — many local minima.

---

## ⏭️ Next Up:

We’ll dive into the **mathematical expressions** behind gradient descent to implement it step-by-step.

# ⚙️ Gradient Descent: Implementation Summary

## 📌 Goal

Minimize the cost function **J(w, b)** by updating parameters **w** and **b** iteratively.

---

## 🔁 Update Rules

```python
# Gradient Descent Updates
w = w - α * (∂J/∂w)
b = b - α * (∂J/∂b)
```

temp*w = w - α * ∂J/∂w
temp*b = b - α * ∂J/∂b

w = temp_w
b = temp_b

# Wrong Implementation

temp*w = w - α * ∂J/∂w
w = temp*w # Updated too early
temp_b = b - α * ∂J(w,b)/∂b using updated w
b = temp_b

# 🧠 Gradient Descent – Intuition Behind Derivatives

## 🔁 What Gradient Descent Does:

- Repeatedly updates the model parameters `w` and `b` to reduce the cost function `J(w, b)`.
- Uses the formula:

  ```
  w := w - α * (dJ(w)/dw)
  ```

  - `α`: learning rate (step size)
  - `dJ(w)/dw`: derivative of the cost function with respect to `w`

---

## 📉 Understanding Derivatives Visually:

- The **derivative** gives the **slope** of the cost function at a point.
- Think of the **tangent line** touching the curve at that point:
  - If **slope is positive**: move left (decrease `w`)
  - If **slope is negative**: move right (increase `w`)
- This helps push `w` **closer to the minimum** of the cost function.

---

## 💡 Key Intuition:

- The derivative tells you **which direction** to move and **how steeply**.
- If:
  - `dJ(w)/dw > 0`, then `w` decreases
  - `dJ(w)/dw < 0`, then `w` increases

---

## ⚠️ Coming Up Next:

- Learn how the **learning rate `α`** affects convergence:
  - Too small → slow learning
  - Too large → unstable or overshooting
- Choosing the right `α` is essential for gradient descent to work effectively.

# Gradient Descent for Linear Regression — Summary

## 🧠 Concepts Covered

### Linear Regression Model Recap

- Predicts output using the model: **f(x) = w \* x + b**

### Squared Error Cost Function

- Measures error between predicted and actual values:
  \[ J(w, b) = \frac{1}{2m} \sum\_{i=1}^{m} (f(x^{(i)}) - y^{(i)})^2 \]

### Gradient Descent Algorithm

- Used to minimize the cost function.
- Update rules:
  \[ w := w - \alpha \frac{\partial J(w, b)}{\partial w} \]
  \[ b := b - \alpha \frac{\partial J(w, b)}{\partial b} \]

### Derivative Calculations

- Derived using calculus:
  - \( \frac{\partial J(w, b)}{\partial w} = \frac{1}{m} \sum_{i=1}^{m} (f(x^{(i)})
    \frac{\partial J(w, b)}{\partial b}J(w, b)}{\partial b} = \frac{1}{m} \sum\_{i=1}^{m} (f(x^{(i)}) - y^{(i)}) \)

### Implementation Note

- Always **simultaneously update** w and b on each iteration.

### Convexity

- For linear regression using squared error:
  - Cost function is **convex** (bowl-shaped)
  - Always has a **single global minimum**
  - Gradient descent will always converge if learning rate is properly set

---

✅ You now know how to implement gradient descent for linear regression and why it works.
