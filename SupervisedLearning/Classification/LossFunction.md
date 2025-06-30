## 📉 Cost Function for Logistic Regression

### 🧠 Objective

- Measure how well a set of parameters `(w, b)` fits the training data
- Enable gradient descent to find optimal parameters

---

### ❌ Why Squared Error Doesn’t Work

- Squared error cost (used in linear regression):
  \[
  J(w, b) = \frac{1}{2m} \sum\_{i=1}^m (f(x^{(i)}) - y^{(i)})^2
  \]
- Problem:
  - For logistic regression (nonlinear `f(x)`), this leads to a **non-convex cost surface**
  - Gradient descent can get stuck in **local minima**

---

### ✅ Logistic (Cross-Entropy) Loss

#### Per-example Loss:

\[
L(f(x), y) =
\begin{cases}

- \log(f(x)) & \text{if } y = 1 \\
- \log(1 - f(x)) & \text{if } y = 0
  \end{cases}
  \]

#### Full Cost Function:

\[
J(w, b) = \frac{1}{m} \sum\_{i=1}^m L(f(x^{(i)}), y^{(i)})
\]

- This **new loss function** is **convex** ✅
- Allows **gradient descent** to reliably reach the **global minimum**

---

### 📊 Intuition Behind Logistic Loss

#### When \( y = 1 \):

- \[
  L = -\log(f(x))
  \]
- Low loss if model predicts a high probability (close to 1)
- Loss → ∞ as prediction → 0

#### When \( y = 0 \):

- \[
  L = -\log(1 - f(x))
  \]
- Low loss if prediction is close to 0
- Loss → ∞ as prediction → 1

#### 🔁 Summary:

| True Label \(y\) | Model Prediction \(f(x)\) | Loss |
| ---------------- | ------------------------- | ---- |
| 1                | 0.9                       | Low  |
| 1                | 0.1                       | High |
| 0                | 0.1                       | Low  |
| 0                | 0.9                       | High |

---

### 🧮 Goal of Training

- Find `(w, b)` that **minimize**:
  \[
  J(w, b) = \frac{1}{m} \sum\_{i=1}^m L(f(x^{(i)}), y^{(i)})
  \]
- This results in a **well-fitted model** for classification

---

### 🧪 Lab Preview

- Compare:
  - ❌ Squared error → non-convex cost surface
  - ✅ Logistic loss → smooth, convex surface
- Visualize surface plots and gradients

---

### ✅ Summary

- Squared error isn’t suitable for classification using logistic regression
- **Log loss (cross-entropy)**:
  - Encourages confident, correct predictions
  - Produces convex cost surface
  - Makes gradient descent effective

> 📌 Up Next: Simplifying this cost function and using **gradient descent** to optimize parameters

## 🧮 Simplified Cost Function for Logistic Regression

### 🔁 Recap: Binary Classification

- Output label \( y \in \{0, 1\} \)
- Goal: Find parameters \( w, b \) to minimize cost and make accurate predictions

---

### ❌ Original Loss Function (Casewise Form)

\[
L(f, y) =
\begin{cases}

- \log(f) & \text{if } y = 1 \\
- \log(1 - f) & \text{if } y = 0
  \end{cases}
  \]

---

### ✅ Simplified Unified Loss Function

\[
L(f, y) = -y \cdot \log(f) - (1 - y) \cdot \log(1 - f)
\]

#### Why This Works:

- If \( y = 1 \):  
  \[
  L = -\log(f) \quad (\text{second term becomes 0})
  \]
- If \( y = 0 \):  
  \[
  L = -\log(1 - f) \quad (\text{first term becomes 0})
  \]

> This compact expression simplifies implementation and avoids writing multiple cases in code.

---

### 📉 Cost Function for the Entire Dataset

Let:

- \( m \): Number of training examples
- \( f^{(i)} = f(x^{(i)}) \)

Then:
\[
J(w, b) = \frac{1}{m} \sum*{i=1}^{m} L(f^{(i)}, y^{(i)})
= -\frac{1}{m} \sum*{i=1}^{m} \left[ y^{(i)} \log(f^{(i)}) + (1 - y^{(i)}) \log(1 - f^{(i)}) \right]
\]

---

### 🧠 Why This Cost Function?

- This specific cost is derived from **Maximum Likelihood Estimation (MLE)**.
- It’s:
  - **Statistically grounded**
  - **Convex**, which means gradient descent will find a **global minimum**
  - Widely used in practice

---

### 💻 Optional Lab Preview

- Implement the logistic cost function in code
- Visualize how:
  - A **good decision boundary** leads to **lo**
