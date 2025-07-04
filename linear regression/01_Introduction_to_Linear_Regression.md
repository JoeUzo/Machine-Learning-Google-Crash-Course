# Introduction to Linear Regression

## Table of Contents
1. [What is Linear Regression?](#what-is-linear-regression)
2. [The Linear Regression Equation](#the-linear-regression-equation)
   - [Single Feature Model](#single-feature-model)
   - [Multiple Feature Model](#multiple-feature-model)
3. [Training the Model](#training-the-model)
4. [Key Terms](#key-terms)

---

## What is Linear Regression?
Linear regression is a fundamental statistical and machine learning technique used to model the relationship between a dependent variable (the **label**) and one or more independent variables (the **features**). The goal is to find the "best fit" straight line that describes how the features predict the label.

For example, we can use it to predict a car's fuel efficiency (label) based on its weight (feature). Generally, as a car's weight increases, its fuel efficiency decreases. Linear regression aims to precisely define this relationship with a mathematical model.

> **In-depth:** The term "linear" refers to the fact that the model assumes a linear relationship. This means that a change in an input feature will result in a proportional change in the output label. The model is represented visually as a straight line (in the case of one feature) or a plane/hyperplane (for multiple features).

## The Linear Regression Equation

### Single Feature Model
The equation for a linear regression model with a single feature is:

`y' = b + w₁x₁`

Where:
- **`y'` (y-prime)**: The **predicted label** (the output value our model predicts).
- **`b`**: The **bias** (also known as the y-intercept). This is the value of `y'` when the feature `x₁` is zero. It's a baseline value for our prediction. It is sometimes denoted as `w₀`.
- **`w₁`**: The **weight** of the feature. This is the slope of the line, which determines how much the prediction `y'` changes for a one-unit change in the feature `x₁`.
- **`x₁`**: The **feature** (the input value).

**Example:** For predicting fuel efficiency (`y'`) from car weight (`x₁`), the model might be `y' = 34 + (-4.6)x₁`.
- The **bias (`b`)** is 34. This would be the theoretical miles per gallon for a car with zero weight.
- The **weight (`w₁`)** is -4.6. This means for every additional 1000 pounds of weight, the fuel efficiency is predicted to decrease by 4.6 MPG.

### Multiple Feature Model
Real-world problems often require more than one feature to make accurate predictions. The model can be extended to include multiple features, each with its own weight:

`y' = b + w₁x₁ + w₂x₂ + ... + wₙxₙ`

For example, to predict a car's fuel efficiency more accurately, we could use features like:
- `x₁`: Weight
- `x₂`: Engine displacement
- `x₃`: Horsepower
- `x₄`: Acceleration

Each feature (`x₁`, `x₂`, etc.) would have its own weight (`w₁`, `w₂`, etc.) that represents its unique influence on the final prediction.

## Training the Model
The core of linear regression is the "training" process. During training, the model analyzes the dataset and automatically learns the optimal values for the **bias (`b`)** and the **weights (`w₁`, `w₂`, ...)**.

The goal of training is to find the parameters (bias and weights) that create a "best fit" line—the line that minimizes the overall error between its predictions and the actual label values in the dataset. The parts of the equation that are updated during training are the **bias and weights**.

## Key Terms
- **Label**: The variable we are trying to predict. The "y" variable.
- **Feature**: An input variable used to make predictions. The "x" variable.
- **Linear Regression**: A model that finds a linear relationship between features and a label.
- **Parameter**: The values that the model learns on its own during training. In linear regression, the parameters are the **bias** and **weights**.
- **Bias (`b` or `w₀`)**: The y-intercept of the regression line. The starting point of the prediction.
- **Weight (`w₁`, `w₂`, ...)**: The slope of the line for a specific feature. It represents the strength and direction of that feature's relationship with the label.
