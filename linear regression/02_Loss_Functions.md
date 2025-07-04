# Understanding Loss in Linear Regression

## Table of Contents
1. [What is Loss?](#what-is-loss)
2. [Calculating Loss: L1 and L2](#calculating-loss-l1-and-l2)
3. [Common Loss Functions: MAE and MSE](#common-loss-functions-mae-and-mse)
4. [Choosing a Loss Function: The Role of Outliers](#choosing-a-loss-function-the-role-of-outliers)
5. [Key Terms](#key-terms)

---

## What is Loss?
**Loss** is a number that quantifies how "wrong" a model's prediction is compared to the actual label. It measures the distance or error between the predicted value and the true value. The primary goal of training a machine learning model is to find the parameters (weights and bias) that **minimize this loss**.

Visually, you can think of loss as the length of the arrows from each actual data point to the model's regression line. Shorter arrows mean lower loss and a better-fitting model.

## Calculating Loss: L1 and L2
Since we only care about the magnitude of the error, not its direction (positive or negative), we use methods to remove the sign from the difference between the prediction and the actual value. The two most common approaches are:

1.  **L1 Regularization (Absolute Value):** Takes the absolute value of the difference.
    - `|actual - predicted|`
2.  **L2 Regularization (Squaring):** Squares the difference.
    - `(actual - predicted)²`

> **In-depth: The Impact of Squaring (L2)**
> The key functional difference between L1 and L2 is the squaring operation.
> - **Large Errors:** If the error is large (e.g., 10), squaring it results in a much larger number (100). This means L2 loss penalizes "very wrong" predictions much more heavily than L1 loss.
> - **Small Errors:** If the error is small (e.g., 0.5), squaring it results in an even smaller number (0.25). This means L2 loss is less concerned with tiny errors than L1 loss.

## Common Loss Functions: MAE and MSE
When working with a whole dataset, we average the individual losses across all examples. This leads to the two most common loss functions in regression:

| Loss Type | Definition | Equation |
| :--- | :--- | :--- |
| **Mean Absolute Error (MAE)** | The average of L1 losses across all *N* examples. | `(1/N) * Σ |actual - predicted|` |
| **Mean Squared Error (MSE)** | The average of L2 losses across all *N* examples. | `(1/N) * Σ (actual - predicted)²` |

## Choosing a Loss Function: The Role of Outliers
The choice between MAE and MSE often depends on how you want your model to handle **outliers**. An outlier is a data point that is significantly different from other observations, either in its feature values or in the relationship between its features and label.

Because MSE squares the errors, it is much more sensitive to outliers than MAE. A single data point with a very large error will contribute a massive amount to the total loss, forcing the model to adjust its parameters significantly to reduce that single error.

- **Use MSE when:** You believe outliers are important, represent legitimate (though rare) phenomena, and you want your model to be influenced by them. The resulting model will be pulled closer to the outliers.
- **Use MAE when:** You believe outliers are likely due to errors in the data (e.g., measurement errors) and should be treated as noise. MAE is more robust and will produce a model that better represents the majority of the data points, ignoring the outliers' pull.

**Example:**
- A model trained with **MSE** will be tilted more towards the outliers to minimize the large squared errors they produce.
- A model trained with **MAE** will be more balanced and closer to the bulk of the non-outlier data points.

## Key Terms
- **Loss**: A measure of the difference between a model's prediction and the actual label.
- **L1 Loss**: A loss calculation based on the sum of absolute differences.
- **L2 Loss**: A loss calculation based on the sum of squared differences.
- **Mean Absolute Error (MAE)**: The average L1 loss over an entire dataset. It is less sensitive to outliers.
- **Mean Squared Error (MSE)**: The average L2 loss over an entire dataset. It is more sensitive to outliers.
- **Outlier**: A data point that differs significantly from other observations.
- **Prediction**: The output of the model (`y'`).
