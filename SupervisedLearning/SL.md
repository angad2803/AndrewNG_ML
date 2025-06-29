# Supervised Learning

Supervised learning is a type of machine learning where the model is trained on labeled data. The goal is to learn a mapping from inputs to outputs, so the model can make predictions on new, unseen data.
In supervised learning, the model receives input data \( x \) and learns to map it to the correct output \( y \). This mapping enables the model to predict \( y \) for new instances of \( x \).

## Types of Supervised Learning

### 1. Regression

- **Definition:** Predicts continuous values.
- **Examples:** House price prediction, temperature forecasting.
- **Common Algorithms:** Linear Regression, Polynomial Regression, Support Vector Regression.

**Example:**  
Given features like size and location, predict the price of a house.

### 2. Classification

- **Definition:** Predicts discrete class labels.
- **Examples:** Email spam detection, image recognition (cat vs. dog).
- **Common Algorithms:** Logistic Regression, Decision Trees, Support Vector Machines, k-Nearest Neighbors.

**Example:**  
Given an email, classify it as "spam" or "not spam".

---

| Task           | Output Type | Example                 |
| -------------- | ----------- | ----------------------- |
| Regression     | Continuous  | Predicting house prices |
| Classification | Discrete    | Email spam detection    |

---

## Workflow

1. **Collect labeled data**
2. **Split data** into training and test sets
3. **Train** the model on the training set
4. **Evaluate** the model on the test set
5. **Predict** outputs for new data
