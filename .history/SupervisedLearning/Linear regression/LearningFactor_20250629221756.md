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
