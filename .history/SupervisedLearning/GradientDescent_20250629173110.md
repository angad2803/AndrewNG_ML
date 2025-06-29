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
