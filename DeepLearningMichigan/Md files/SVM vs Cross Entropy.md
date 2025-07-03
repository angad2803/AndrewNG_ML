# 🧠 SVM vs Cross-Entropy Loss

This document compares **Support Vector Machine (SVM)** Loss and **Cross-Entropy Loss**, which are commonly used in classification tasks. Suitable for deep learning and ML revision.

---

## 📘 1. Score Function

Both losses use a score function computed as:

```text
s = W x + b
```

Where:

- `x`: Input vector (e.g., image pixels)
- `W`: Weight matrix
- `b`: Bias vector
- `s`: Class scores (logits)

### 🔹 Code

```python
import numpy as np

def compute_scores(X, W, b):
  """
  X: shape (N, D) - input data
  W: shape (D, C) - weights
  b: shape (C,)   - biases
  Returns: shape (N, C) - class scores
  """
  return np.dot(X, W) + b
```

## 🔹 1. SVM Loss (Multiclass Hinge Loss)

**Goal:** Ensure the score of the correct class is higher than the scores of all incorrect classes by a margin Δ (typically set to 1).

### 🔣 SVM (Multiclass Hinge) Loss Formula

```text
L_i = sum_{j ≠ y_i} max(0, s_j - s_{y_i} + Δ)
```

<details>
<summary>LaTeX (for GitHub rendering):</summary>

```math
L_i = \sum_{j \ne y_i} \max(0, s_j - s_{y_i} + \Delta)
```

</details>

### 🧠 Explanation

- Encourages the correct class score `s_{y_i}` to be **greater than all others** by at least a margin Δ.
- If any incorrect class score `s_j` is **too close** or **greater** than `s_{y_i} - Δ`, the model is **penalized**.
- If the margin is respected, loss is **zero**.

## 🔹 2. Cross-Entropy Loss (with Softmax)

**Goal:** Convert scores into probabilities and maximize the confidence for the correct class.

### 🔣 Softmax Formula

```text
P(y_i) = exp(s_{y_i}) / sum_j exp(s_j)
```

<details>
<summary>LaTeX (for GitHub rendering):</summary>

```math
P(y_i) = \frac{\exp(s_{y_i})}{\sum_j \exp(s_j)}
```

</details>

### 🔣 Cross-Entropy Formula

```text
L_i = -log P(y_i) = -log (exp(s_{y_i}) / sum_j exp(s_j))
```

<details>
<summary>LaTeX (for GitHub rendering):</summary>

```math
L_i = -\log P(y_i) = -\log \left( \frac{\exp(s_{y_i})}{\sum_j \exp(s_j)} \right )
```

</details>
