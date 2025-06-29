# Feature Engineering in Machine Learning

## Why Feature Engineering?

The **choice of features** can dramatically impact the performance of a learning algorithm.

> In real-world applications, **designing effective features** is often more important than the learning algorithm itself.

---

## Example: Predicting House Prices

### Given Features:

- \( x_1 \): Width of the lot (frontage)
- \( x_2 \): Depth of the lot

### Initial Model:

Linear regression with:
\[
f\_{\mathbf{w}, b}(x) = w_1 x_1 + w_2 x_2 + b
\]

This model treats **frontage** and **depth** independently.

---

## Improved Feature via Engineering

### New Insight:

- The **area** of the plot might be more predictive than just width or depth.
- Area = \( x_1 \times x_2 \)

### Define a New Feature:

\[
x_3 = x_1 \times x_2
\]

### New Model:

\[
f\_{\mathbf{w}, b}(x) = w_1 x_1 + w_2 x_2 + w_3 x_3 + b
\]

Now, the model can **learn the importance** of width, depth, and area independently and choose what matters most.

---

## What Is Feature Engineering?

**Feature engineering** is the process of:

- Creating new features using **domain knowledge**
- **Combining or transforming** raw features to better represent the data
- Making patterns **easier to learn** by the model

This can include:

- Polynomial features
- Interaction terms
- Log, square root, or exponential transformations
- Binning or categorization
- Domain-specific computations (e.g., area, speed = distance/time)

---

## Why It Works

- Helps your model **learn non-obvious relationships**
- Reduces model complexity while improving **predictive accuracy**
- Essential for algorithms like linear regression which assume a **linear relationship** between inputs and outputs

---

## Summary

| Concept            | Description                                             |
| ------------------ | ------------------------------------------------------- |
| Raw Features       | Original data inputs (e.g., width, depth)               |
| Engineered Feature | Computed from raw features (e.g., area = width × depth) |
| Purpose            | Capture better signal for prediction                    |
| Benefit            | Improves model accuracy with minimal added complexity   |

✅ **Best Practice**: Use your domain knowledge to create **new, meaningful features** that better represent the underlying patterns in the data.

➡️ Next: Learn how **feature engineering** can help you fit **non-linear (curved)** relationships using linear models!
