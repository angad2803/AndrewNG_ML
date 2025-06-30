# Recognizing Gradient Descent Convergence

## Purpose

Gradient Descent aims to minimize the cost function \( J(w, b) \) by iteratively updating parameters. To verify if it's converging (i.e., approaching the global minimum), we can monitor the behavior of the **cost function over iterations**.

---

## The Learning Curve

- A **learning curve** plots the **cost \( J \)** (vertical axis) against the **number of iterations** (horizontal axis).
- After each iteration (i.e., one full update of all parameters), compute and plot the cost.
- If gradient descent is working correctly:
  - The cost **should consistently decrease** over iterations.
  - If cost **increases**, it's a sign of:
    - **Too large a learning rate \( \alpha \)**
    - Or a **bug** in the implementation

---

## Example Interpretation

- A smooth, downward-sloping curve indicates healthy convergence.
- When the curve **flattens out**, gradient descent has **converged**.
- Different applications may require very different numbers of iterations to converge:
  - Some converge in **30 iterations**
  - Others may take **1,000+ or even 100,000**

---

## Convergence Criteria

### 1. **Manual Visualization (Preferred)**

- Plot cost after every iteration.
- Visually inspect when the curve levels off.

### 2. **Automatic Convergence Test**

- Define a small threshold \( \varepsilon \) (e.g., \( \varepsilon = 0.001 \))
- If:  
  \( J^{(t)} - J^{(t+1)} < \varepsilon \)  
  → declare convergence

- **Note**: Selecting a good \( \varepsilon \) is tricky.
- **Tip**: Visual inspection is often more reliable.

---

## Summary

| Metric                   | What it Tells You                      |
| ------------------------ | -------------------------------------- |
| Decreasing Cost \( J \)  | Gradient Descent is working            |
| Increasing Cost          | Likely too large \( \alpha \) or a bug |
| Flat Curve (No Decrease) | Likely Converged                       |
| Sudden Jumps in Cost     | Learning rate may be too high          |

### ✅ Best Practice:

> Always **plot the learning curve** when training a model with gradient descent.

➡️ Up next: Learn **how to choose a good learning rate \( \alpha \)** for efficient training.

# Choosing a Good Learning Rate (α) in Gradient Descent

## Why It Matters

The learning rate \( \alpha \) controls the **step size** of gradient descent:

- **Too small** → very slow convergence
- **Too large** → may overshoot the minimum, fail to converge, or even diverge

---

## Diagnosing Learning Rate Issues

### 1. **Oscillating or Increasing Cost**

- If the **cost increases** or **oscillates**, gradient descent isn’t working.
- Likely reasons:
  - \( \alpha \) is **too large**
  - **Sign error** in update equation  
    (e.g., using `+ α ∇J` instead of `- α ∇J`)

### 2. **Smooth Convergence**

- If cost **decreases steadily** at every iteration:
  - \( \alpha \) is **small but correct**
  - Update steps are **stable**
  - May be **too slow**, though correct

---

## Visual Debugging: Plot the Learning Curve

- Plot cost \( J(w, b) \) vs. iterations
- If:
  - Curve decreases → ✅ working
  - Curve jumps up/down → 🔥 learning rate too high
  - Curve flattens quickly → ✅ converged
  - Curve flat from start → ⚠️ learning rate too low

---

## Debugging Tip

To verify correctness of your gradient descent code:

- Temporarily set a **very small \( \alpha \)** (e.g., 0.0001)
- If cost **still increases**, it's likely a **bug in your code**

---

## How to Choose a Good Learning Rate

Try several \( \alpha \) values, increasing each time by a factor of ~3:

```text
Try: 0.001 → 0.003 → 0.01 → 0.03 → 0.1 → ...
```
