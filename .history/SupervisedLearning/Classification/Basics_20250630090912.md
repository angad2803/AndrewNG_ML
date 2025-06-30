## 🧠 Week 3: Classification & Logistic Regression

### 🔹 What is Classification?

- Predicts **categories**, not numbers (unlike regression)
- **Binary classification**: Only two possible outputs (e.g., spam/not spam)
  - Labels often: `0` (negative) or `1` (positive)

### 🔸 Examples:

- Spam detection: Is email spam? → Yes (1) / No (0)
- Fraud detection: Is transaction fraudulent?
- Medical: Is tumor malignant?

### ❌ Why Not Use Linear Regression for Classification?

- Linear regression outputs values beyond 0 and 1
- Applying a threshold (e.g., 0.5) **kind of works**, but:
  - One outlier can **shift the decision boundary**
  - Not robust for classification tasks

### ✅ Logistic Regression to the Rescue

- Output always between **0 and 1**
- Solves classification problems better than linear regression
- Despite the name, **logistic regression is used for classification**

### ⚠️ Terms to Know:

- **Positive class (1)** = e.g., spam, malignant
- **Negative class (0)** = e.g., not spam, benign
- **Decision Boundary**: The threshold dividing class 0 and 1

> 🔍 Explore the optional lab to visualize why linear regression fails in classification.
