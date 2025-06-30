## 📚 Logistic Regression: A Powerful Classification Algorithm

### 🔸 Purpose

- Used for **binary classification** problems (e.g., tumor: benign or malignant)
- Outputs a value between **0 and 1**, representing the **probability** that `y = 1`

---

### 🧮 The Logistic Regression Model

#### 1. **Sigmoid (Logistic) Function**

- Formula:  
  \[
  g(z) = \frac{1}{1 + e^{-z}}
  \]
- Properties:
  - Output: Always between **0 and 1**
  - S-shaped curve (asymptotes at 0 and 1)
  - Passes through **0.5 when z = 0**

#### 2. **Model Formula**

- Linear part:  
  \[
  z = w \cdot x + b
  \]
- Apply sigmoid:  
  \[
  f(x) = g(z) = \frac{1}{1 + e^{-(w \cdot x + b)}}
  \]

---

### 📈 Example: Tumor Classification

- Input: Tumor size (x)
- Output:  
  \[
  f(x) = 0.7 \Rightarrow \text{70% probability of malignant (y = 1)}
  \]
- Interpretation:  
  \[
  P(y = 1 | x) = 0.7,\quad P(y = 0 | x) = 0.3
  \]

---

### 🔹 Notation (FYI)

- You may see:  
  \[
  f(x) = P(y = 1 \mid x; w, b)
  \]
- Don’t worry about the `|` or `;` for now — just know it means:
  > Probability of y = 1 given input x and parameters w, b

---

### ✅ Summary

- **Logistic regression** applies a sigmoid to a linear model to estimate probabilities.
- It's one of the most used models in **fraud detection, medical diagnosis, ad placement**, etc.
- It's more robust than linear regression for classification tasks.

> 💡 Explore the optional lab to see how the sigmoid improves classification over linear regression.
