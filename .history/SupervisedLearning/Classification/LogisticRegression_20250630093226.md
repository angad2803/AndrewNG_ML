## 📚 Logistic Regression: A Powerful Classification Algorithm

### 🔸 Purpose

- Used for **binary classification** problems (e.g., tumor: benign or malignant)
- Outputs a value between **0 and 1**, representing the **probability** that `y = 1`

---

### 🧮 The Logistic Regression Model

#### 1. **Sigmoid (Logistic) Function**

- Formula:
  ```
  g(z) = 1 / (1 + exp(-z))
  ```
- Properties:
  - Output: Always between **0 and 1**
  - S-shaped curve (asymptotes at 0 and 1)
  - Passes through **0.5 when z = 0**

#### 2. **Model Formula**

- Linear part:
  ```
  z = w * x + b
  ```
- Apply sigmoid:
  ```
  f(x) = g(z) = 1 / (1 + exp(-(w * x + b)))
  ```

---

### 📈 Example: Tumor Classification

- Input: Tumor size (`x`)
- Output:
  ```
  f(x) = 0.7  =>  70% probability of malignant (y = 1)
  ```
- Interpretation:
  ```
  P(y = 1 | x) = 0.7,   P(y = 0 | x) = 0.3
  ```

---

### 🔹 Notation (FYI)

- You may see:
  ```
  f(x) = P(y = 1 | x; w, b)
  ```
- Don’t worry about the `|` or `;` for now — just know it means:
  > Probability of y = 1 given input x and parameters w, b

---

### ✅ Summary

- **Logistic regression** applies a sigmoid to a linear model to estimate probabilities.
- It's one of the most used models in **fraud detection, medical diagnosis, ad placement**, etc.
- It's more robust than linear regression for classification tasks.

> 💡 Explore the optional lab to see how the sigmoid improves classification over linear regression.

## 🎯 Logistic Regression: Decision Boundary

### 🔁 Recap: Logistic Regression Model

- **Model Output**:  
  \[
  f(x) = g(z) = \frac{1}{1 + e^{-z}}, \quad \text{where } z = w \cdot x + b
  \]
- Interpreted as:  
  \[
  P(y = 1 \mid x; w, b)
  \]
- Common decision threshold:
  - If \( f(x) \geq 0.5 \) → Predict \( y = 1 \)
  - Else → Predict \( y = 0 \)

---

### 🟦 Decision Boundary

- **Boundary occurs when**:  
  \[
  f(x) = 0.5 \Rightarrow z = 0 \Rightarrow w \cdot x + b = 0
  \]
- This equation defines a **hyperplane** (or a line in 2D):
  - One side → predict \( y = 1 \)
  - Other side → predict \( y = 0 \)

---

### 📊 Example with 2 Features (Linear Boundary)

Given:

- \( w_1 = 1, \quad w_2 = 1, \quad b = -3 \)

Then:

- \( z = x_1 + x_2 - 3 \)
- **Decision boundary**:  
  \[
  x_1 + x_2 = 3
  \]

---

### 🔁 Nonlinear Decision Boundary (Using Polynomials)

Using polynomial features:

- \( z = w_1 x_1^2 + w_2 x_2^2 + b \)
- Example: \( w_1 = 1, w_2 = 1, b = -1 \)

Then:

- Decision boundary:
  \[
  x_1^2 + x_2^2 = 1 \Rightarrow \text{a circle}
  \]
- Predict \( y = 1 \) outside the circle  
  Predict \( y = 0 \) inside

---

### 🌀 Complex Boundaries (Higher-Order Polynomials)

Using features like:
\[
z = w_1 x_1 + w_2 x_2 + w_3 x_1^2 + w_4 x_1 x_2 + w_5 x_2^2
\]

- Can learn **ellipses**, **irregular shapes**, or even **wavy decision boundaries**

---

### ⚠️ Important:

- Without polynomial features, logistic regression always gives a **linear decision boundary**
- Adding polynomial terms increases model flexibility

---

### ✅ Summary

| Feature Type         | Decision Boundary Type  |
| -------------------- | ----------------------- |
| Only linear (x₁, x₂) | Straight line (linear)  |
| Polynomials added    | Circle, ellipse, curves |
| High-degree terms    | Very complex, flexible  |

> 📌 Optional Lab: Try plotting these to **visualize decision boundaries** yourself.

Next: Training logistic regression using a **cost function** and **gradient descent**.
