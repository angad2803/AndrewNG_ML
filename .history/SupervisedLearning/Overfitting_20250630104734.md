## 📉 Underfitting vs. Overfitting in Machine Learning

---

### 🎯 Objective

Understand **underfitting**, **overfitting**, and how they affect your model's **generalization** to unseen data.

---

### 🧠 Key Concepts

| Concept          | Description                                                                   |
| ---------------- | ----------------------------------------------------------------------------- |
| **Underfitting** | Model is too simple to capture patterns in training data                      |
| **Overfitting**  | Model is too complex and fits the training data too well, including noise     |
| **Just Right**   | Model fits the training data well and generalizes to unseen examples          |
| **Bias**         | Error due to overly simplistic assumptions (underfitting)                     |
| **Variance**     | Error due to sensitivity to small fluctuations in training data (overfitting) |

---

### 🏠 Housing Price Prediction Example

#### 📉 Underfitting (High Bias)

- Linear model fits a straight line through data
- Misses non-linear patterns
- Model has high training error

#### ✅ Just Right

- Quadratic model captures the trend in housing prices better
- Fits training data fairly well
- Likely to generalize well on new examples

#### 📈 Overfitting (High Variance)

- Fourth-order polynomial fits training data **perfectly**
- Very "wiggly" curve with poor real-world logic
- Will generalize **poorly** to new unseen data

---

### ⚖️ Bias vs. Variance

|                | High Bias (Underfitting)    | High Variance (Overfitting)    |
| -------------- | --------------------------- | ------------------------------ |
| Model          | Too simple                  | Too complex                    |
| Training Error | High                        | Low                            |
| Test Error     | High                        | High                           |
| Sensitivity    | Insensitive to data changes | Very sensitive to data changes |
| Generalization | Poor                        | Poor                           |

---

### 🧪 Classification Example: Tumor Detection

#### Underfitting (High Bias)

- Simple linear decision boundary using logistic regression
- Doesn't classify well; misses data patterns

#### Just Right

- Use quadratic features (like \( x_1^2 \), \( x_2^2 \), etc.)
- Elliptical boundary separates data well
- Classifies accurately and generalizes well

#### Overfitting (High Variance)

- Complex, high-order polynomial decision boundary
- Twists to perfectly classify all training points
- Will fail on slightly different/new data

---

### 🧠 Mental Model: Goldilocks Analogy

- **Too simple** (underfitting) → ❄️ Cold porridge (not useful)
- **Too complex** (overfitting) → 🔥 Hot porridge (not useful)
- **Just right** → 🌡️ Porridge that’s perfect to eat (generalizes well)

---

### ✅ Summary

- **Underfitting / High Bias**: Model can't even fit training data properly.
- **Overfitting / High Variance**: Model fits training data too well, poor generalization.
- **Goal**: Choose a model that's **just right** in complexity.

> 🎯 In the next video, you'll learn how to fix overfitting using **regularization**, a powerful and commonly used technique.

## 🛠️ Addressing Overfitting in Machine Learning

---

### 🤔 What is Overfitting?

Overfitting occurs when a model learns the training data **too well**, including noise or random fluctuations, leading to **poor generalization** on new data.

---

### 🧩 3 Main Ways to Fix Overfitting

---

### 1. 📈 Get More Training Data

- **Best tool** to fight overfitting.
- More data helps the model **learn a smoother, less wiggly function**.
- Especially effective if you already have a complex model.
- ✅ Pros: Doesn't reduce feature information.
- ❌ Cons: Sometimes **not possible** due to data scarcity.

---

### 2. ✂️ Use Fewer Features (Feature Selection)

- Drop irrelevant or less important features.
- Example: Instead of using 100 features, choose only the most useful ones like `size`, `bedrooms`, and `age`.
- Helps avoid high variance due to **too many inputs** and **too little data**.

> 🔍 This is called **feature selection**.  
> Later in Course 2, you'll see **automated ways** to do this.

- ✅ Pros: Simple and intuitive.
- ❌ Cons: You may lose useful information if relevant features are removed.

---

### 3. 🧪 Apply Regularization (Key Technique)

- Encourages **smaller parameter values (w₁, w₂, ..., wₙ)**.
- Doesn't force parameters to 0 (like feature selection), just **shrinks** them.
- Helps maintain all features while **reducing their effect** if not helpful.

#### 🔧 Key Ideas:

- **Big weights** can lead to overly complex models → overfitting.
- **Smaller weights** = smoother decision boundary → better generalization.
- Usually **don’t regularize `b`**, only weights `w₁...wₙ`.

> 📌 Regularization is one of the most powerful and commonly used tools, especially in **neural networks**.

---

### 🧪 Optional Lab Features:

- Experiment with:
  - Polynomial degree: `x`, `x²`, `x³`, etc.
  - Adding/removing data points
  - Selecting features
- Observe model behavior in:
  - Regression
  - Classification

---

### ✅ Summary Table

| Method            | Description                                                      | When to Use                            |
| ----------------- | ---------------------------------------------------------------- | -------------------------------------- |
| Get More Data     | Expands the training set to reduce variance                      | If more data is available              |
| Feature Selection | Use fewer, more relevant features                                | When many features but little data     |
| Regularization    | Shrinks weights to reduce complexity without discarding features | Almost always – works with many models |

---

### 🔜 Coming Up Next...

- You'll learn how to **formulate regularization mathematically**, and apply it to:
  - Linear Regression
  - Logistic Regression
  - Later, Neural Networks
