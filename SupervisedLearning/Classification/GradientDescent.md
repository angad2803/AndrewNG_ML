## 🚀 Gradient Descent for Logistic Regression (Full Implementation)

---

### 🎯 Objective

Minimize the **cost function** \( J(w, b) \) to find the best parameters **w** and **b** using **gradient descent**.

---

### 🧠 Logistic Regression Recap

- **Prediction Function**:
  \[
  f(x) = \sigma(w \cdot x + b) = \frac{1}{1 + e^{-(w \cdot x + b)}}
  \]

- **Cost Function**:
  \[
  J(w, b) = -\frac{1}{m} \sum\_{i=1}^m \left[ y^{(i)} \log(f^{(i)}) + (1 - y^{(i)}) \log(1 - f^{(i)}) \right]
  \]

---

### 🔁 Gradient Descent Update Rules

Update each parameter using:

- **For each weight \( w_j \):**
  \[
  w*j := w_j - \alpha \cdot \frac{1}{m} \sum*{i=1}^{m} (f^{(i)} - y^{(i)}) \cdot x_j^{(i)}
  \]

- **For bias \( b \):**
  \[
  b := b - \alpha \cdot \frac{1}{m} \sum\_{i=1}^{m} (f^{(i)} - y^{(i)})
  \]

Where:

- \( \alpha \) is the **learning rate**
- \( f^{(i)} \) is the **prediction** for training example \( i \)

> ⚠️ Use **simultaneous updates**: calculate all gradients first, then update all parameters together.

---

### 🤔 Why It Looks Like Linear Regression

Although the update rules **look identical** to linear regression, they are **not** the same:

|                       | Linear Regression       | Logistic Regression                         |
| --------------------- | ----------------------- | ------------------------------------------- |
| Prediction \( f(x) \) | \( w \cdot x + b \)     | \( \sigma(w \cdot x + b) \) (sigmoid)       |
| Output Range          | \( (-\infty, \infty) \) | \( (0, 1) \) (interpreted as probabilities) |
| Use Case              | Regression              | Binary Classification                       |

---

### ⚡ Optimization Tips

- ✅ **Feature Scaling**  
  Scale features to similar ranges (e.g., -1 to 1)  
  → Helps **faster convergence** of gradient descent

- ✅ **Vectorization**  
  Use matrix operations to improve computational efficiency  
  → Covered in **optional labs**

---

### 🧪 Optional Labs

1. **Visualize** gradient descent:

   - Sigmoid function
   - 2D contour plots
   - 3D cost surface plots
   - Learning curves

2. **Scikit-Learn** integration:
   - Use `sklearn.linear_model.LogisticRegression`
   - Very popular in industry (widely used in companies)

---

### 🏁 Summary

| Component        | Purpose                               |
| ---------------- | ------------------------------------- |
| Sigmoid          | Converts scores to probabilities      |
| Cost Function    | Measures how good your parameters are |
| Gradient Descent | Optimizes parameters \( w, b \)       |
| Feature Scaling  | Speeds up convergence                 |
| Vectorization    | Makes the implementation faster       |

> 🎉 You now fully understand and can implement **logistic regression** using **gradient descent** from scratch!

---

### ✅ What’s Next?

- Practice labs to reinforce the implementation
- Scikit-learn for practical, real-world logistic regression
