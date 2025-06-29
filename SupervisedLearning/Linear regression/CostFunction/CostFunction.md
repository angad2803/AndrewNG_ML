# Cost Function in Linear Regression

## Overview

The cost function measures how well a linear model fits training data. For a model `f(x) = w * x + b`, we minimize `J(w, b)` to find optimal parameters.

## Simplified Model (b = 0)

When we set `b = 0`, the model becomes `f(x) = w * x` with cost function:

```
J(w) = (1/2m) * Σ (w * xᵢ - yᵢ)²
```

This simplification helps us visualize how the cost function works by focusing on just one parameter.

## Understanding the Cost Function Intuition

### The Goal

- **Objective**: Find values for w (and b) that minimize the cost function J
- **Mathematical notation**: `minimize J(w, b)`
- **Intuition**: The cost function measures the difference between model predictions and actual values

### Visual Relationship Between Model and Cost

- **Left graph**: Shows the model `f(x) = w * x` with different w values
- **Right graph**: Shows the cost function `J(w)` for different w values
- **Connection**: Each value of w produces a different line, which corresponds to a specific point on the cost function

## Detailed Cost Function Analysis

### Using Dataset: (1,1), (2,2), (3,3)

#### Case 1: w = 1 (Perfect Fit)

- **Model**: `f(x) = x` (line with slope 1)
- **Predictions**:
  - f(1) = 1, f(2) = 2, f(3) = 3
- **Errors**: All zero (perfect predictions)
- **Cost**: J(1) = 0
- **Result**: Line passes through all data points perfectly

#### Case 2: w = 0.5 (Good Fit)

- **Model**: `f(x) = 0.5x` (line with slope 0.5)
- **Predictions and Errors**:
  - f(1) = 0.5 → Error = (0.5 - 1)² = 0.25
  - f(2) = 1.0 → Error = (1 - 2)² = 1.0
  - f(3) = 1.5 → Error = (1.5 - 3)² = 2.25
- **Total squared error**: 3.5
- **Cost**: J(0.5) = 3.5 / (2 × 3) ≈ 0.58
- **Result**: Line fits data reasonably well

#### Case 3: w = 0 (Poor Fit)

- **Model**: `f(x) = 0` (horizontal line on x-axis)
- **Predictions and Errors**:
  - f(1) = 0 → Error = (0 - 1)² = 1
  - f(2) = 0 → Error = (0 - 2)² = 4
  - f(3) = 0 → Error = (0 - 3)² = 9
- **Total squared error**: 14
- **Cost**: J(0) = 14 / 6 ≈ 2.33
- **Result**: Line doesn't fit data well

#### Case 4: w = -0.5 (Very Poor Fit)

- **Model**: `f(x) = -0.5x` (downward sloping line)
- **Cost**: J(-0.5) ≈ 5.25
- **Result**: Line fits data very poorly

## Cost Function Visualization

| w value  | Cost J(w)      | Result        | Visual Description                 |
| -------- | -------------- | ------------- | ---------------------------------- |
| w = 1    | J(1) = 0       | Perfect fit   | Line passes through all points     |
| w = 0.5  | J(0.5) ≈ 0.58  | Good fit      | Line close to data points          |
| w = 0    | J(0) ≈ 2.33    | Poor fit      | Horizontal line, misses all points |
| w = -0.5 | J(-0.5) ≈ 5.25 | Very poor fit | Downward line, opposite trend      |

## Key Insights

### How the Cost Function Works

1. **Each value of w** → **Different straight line** → **Different cost J(w)**
2. **Cost increases** as predictions deviate from actual values
3. **Cost function creates a curve** showing how good each w value is
4. **Goal**: Find w that produces the smallest possible J(w)

### The Optimization Process

- **Linear regression algorithm** systematically tries different w values
- **For each w**, it calculates the corresponding cost J(w)
- **It finds the w value** that minimizes the cost function
- **In this example**: w = 1 gives the optimal solution

### Mathematical Foundation

- **Cost function formula**: `J(w) = (1/2m) * Σ (w * xᵢ - yᵢ)²`
- **Squared error**: Penalizes larger errors more heavily
- **Normalization factor**: `1/2m` averages the errors across all training examples

## From Simplified to Full Model

### Current Simplified Version

- **Model**: `f(x) = w * x` (only one parameter)
- **Cost**: `J(w)` (function of one variable)
- **Visualization**: 2D plot showing cost vs. w

### Next: Full Model

- **Model**: `f(x) = w * x + b` (two parameters)
- **Cost**: `J(w, b)` (function of two variables)
- **Visualization**: 3D plot showing cost vs. w and b

## Summary

The cost function is the core mechanism that drives linear regression:

- **It measures model performance** by calculating prediction errors
- **It guides parameter optimization** by showing which values work best
- **It enables automated learning** by providing a mathematical objective to minimize
- **The goal is always**: Find parameters that make J as small as possible

In the next video, we'll extend this understanding to the full model with both w and b parameters, using 3D visualizations to see how the cost function behaves in higher dimensions.
