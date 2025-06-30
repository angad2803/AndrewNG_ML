# 📊 Multiple Linear Regression — Summary

## 🔹 What’s New This Week?

- You're now learning how to make **linear regression faster and more powerful**.
- You'll explore **multiple features** instead of just one.

---

## 🏠 From One Feature to Many

- **Original model**:
  - One feature (`x`) → `f_wb(x) = w * x + b`
- **Expanded model**:
  - Multiple features like:
    - `x₁`: size of house
    - `x₂`: number of bedrooms
    - `x₃`: number of floors
    - `x₄`: age of home
  - New model:  
    `f_wb(x) = w₁x₁ + w₂x₂ + w₃x₃ + w₄x₄ + b`

---

## 🧮 Notation

- `n`: number of features (e.g., 4)
- `X⁽ⁱ⁾`: vector of features for the *i*th training example
- `X⁽ⁱ⁾ⱼ`: *j*th feature of the *i*th example
- `w = [w₁, w₂, ..., wₙ]`: weight vector (parameters)
- `x = [x₁, x₂, ..., xₙ]`: feature vector
- `b`: bias (intercept)
- Arrows over `x` and `w` → indicate they are vectors

---

## 🔢 Model Interpretation

Example model:

```
f_wb(x) = 0.1 * x₁ + 4 * x₂ + 10 * x₃ - 2 * x₄ + 80
```

Interpreted as:

- Base price = $80,000
- +$100 per sq ft (`0.1 × $1000`)
- +$4000 per bedroom
- +$10,000 per floor
- -$2000 per year of age

---

## ➗ Dot Product Notation

- Dot product: `w ⋅ x = w₁x₁ + w₂x₂ + ... + wₙxₙ`
- Final model:  
  `f_wb(x) = w ⋅ x + b`

---

## 📘 Terms

| Term                           | Meaning                                       |
| ------------------------------ | --------------------------------------------- |
| **Univariate Regression**      | One feature                                   |
| **Multiple Linear Regression** | Multiple input features                       |
| **Multivariate Regression**    | _Not_ used here; refers to multiple _outputs_ |

---

## ✅ What’s Next?

> You’ll learn about **vectorization**, a trick to make implementation more efficient and elegant.
