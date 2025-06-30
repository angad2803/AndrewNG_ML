# Polynomial Regression & Advanced Feature Engineering

## 🚀 Goal:

Extend **linear regression** to capture **non-linear** relationships using **feature engineering**, specifically **polynomial regression**.

---

## 📈 Problem Example:

- **Input Feature (x):** House size (in square feet)
- Data does **not** follow a straight line.

### ❌ Linear Fit:

\[
f(x) = w_1x + b
\]
Too simple. Doesn’t capture curvature in data.

---

## ✅ Polynomial Regression

### Quadratic Model:

\[
f(x) = w_1x + w_2x^2 + b
\]

- Fits a curve.
- Problem: may predict **decreasing** prices at large x (not realistic for housing prices).

### Cubic Model:

\[
f(x) = w_1x + w_2x^2 + w_3x^3 + b
\]

- Allows U-shaped or S-shaped curves.
- Better fit in many real-world datasets.

### General Form:

\[
f(x) = w_1x + w_2x^2 + \dots + w_nx^n + b
\]

---

## 🛠️ Feature Engineering Recap

| Technique               | Example                   | Use Case                            |
| ----------------------- | ------------------------- | ----------------------------------- |
| **Multiplication**      | \( x_3 = x_1 \cdot x_2 \) | Area = Width × Depth                |
| **Power terms**         | \( x^2, x^3 \)            | Polynomial regression               |
| **Root transformation** | \( \sqrt{x} \)            | Diminishing returns in large inputs |
| **Log transformation**  | \( \log(x) \)             | Skewed distributions                |

---

## ⚠️ Feature Scaling Is Critical!

- Original \( x \) range: 1 – 1000
- \( x^2 \) range: 1 – 1,000,000
- \( x^3 \) range: 1 – 1,000,000,000

Large feature ranges lead to:

- Poor gradient descent performance
- Skewed cost surfaces

✅ **Normalize** all features to comparable ranges (e.g., mean normalization or Z-score normalization).

---

## 🧠 Key Insight:

> Polynomial regression is **still linear in the parameters**, but **non-linear in the input**.

This means you can use **linear regression algorithms** on polynomial features!

---

## 💡 Tools & Practice

- Try polynomial features in the lab.
- Use libraries like **Scikit-learn**:
  ```python
  from sklearn.preprocessing import PolynomialFeatures
  from sklearn.linear_model import LinearRegression
  ```
