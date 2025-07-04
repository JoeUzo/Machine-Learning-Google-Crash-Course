# Gradient Descent: Minimizing Loss

## Table of Contents
1. [What is Gradient Descent?](#what-is-gradient-descent)
2. [The Iterative Process of Gradient Descent](#the-iterative-process-of-gradient-descent)
3. [Monitoring Training: The Loss Curve](#monitoring-training-the-loss-curve)
4. [Convergence and Convex Functions](#convergence-and-convex-functions)
5. [Key Terms](#key-terms)

---

## What is Gradient Descent?
**Gradient descent** is the core optimization algorithm used to train a linear regression model. Its purpose is to systematically and iteratively find the optimal values for the model's parameters (the **weights** and **bias**) that result in the minimum possible **loss**.

Think of it as a process of trial and error, but a very intelligent one. It doesn't guess randomly; it uses the "gradient" (the derivative or slope of the loss function) to figure out which direction to adjust the parameters to make the model better.

## The Iterative Process of Gradient Descent
The algorithm starts by initializing the weights and bias to random (or zero) values. It then repeats the following steps in a loop for a set number of **iterations**:

1.  **Calculate the Loss:** The model uses the current weights and bias to make predictions on the training data and calculates the loss (e.g., MSE) based on how wrong those predictions are.
2.  **Determine the Direction (Calculate the Gradient):** The algorithm calculates the gradient of the loss function. The gradient is a vector that points in the direction of the steepest *increase* in loss. Therefore, to *decrease* the loss, the algorithm will move the parameters in the *opposite* direction of the gradient.
3.  **Update Parameters:** The model updates the weights and bias by taking a small step in the negative gradient direction. This step size is controlled by a hyperparameter called the **learning rate**.
4.  **Repeat:** The process goes back to step 1 and continues until the loss stops decreasing significantly, a state known as **convergence**.

## Monitoring Training: The Loss Curve
A **loss curve** is a crucial tool for understanding the training process. It's a graph that plots the model's loss on the y-axis against the number of training iterations on the x-axis.

A typical loss curve shows:
- **Rapid initial improvement:** The loss drops sharply during the first few hundred iterations as the model quickly learns the basic patterns in the data.
- **Gradual refinement:** The curve becomes less steep as the model makes smaller, more refined adjustments to its parameters.
- **Convergence:** The curve flattens out, indicating that further training iterations are yielding little to no improvement in the loss. At this point, the model has **converged**.

![Typical Loss Curve](https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/convergence.png) A typical loss curve


## Convergence and Convex Functions
For linear regression, the loss function (like MSE) creates a **convex** loss surface. A convex surface looks like a bowl or a valley. It has only one global minimum—a single lowest point.

![Link to Convex Loss Surface](https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/convexity.png) A convex loss surface

This property is extremely important because it guarantees that when gradient descent finds a minimum, it has found the *best possible* minimum (the global minimum). There are no other "local minima" (smaller valleys) where the algorithm could get stuck.

When the model converges on this convex surface, we can be confident that it has found the optimal weight and bias values that produce the lowest possible loss for the given training data.

> **In-depth:** The final loss value is almost never zero. The goal is not to achieve zero loss (which would likely mean the model has "overfit" the training data), but to find the *minimum possible loss* that the model can achieve, representing the best possible linear fit for the data.

## Key Terms
- **Gradient Descent**: An iterative optimization algorithm used to find the minimum of a function (in this case, the loss function).
- **Iteration**: A single cycle of the gradient descent process (calculate loss, determine direction, update parameters).
- **Loss Curve**: A graph showing the change in loss over training iterations.
- **Convergence**: The state where the model's loss has stabilized and further training does not significantly improve it.
- **Convex Function**: A function that creates a bowl-shaped curve (or surface) with only one global minimum. The loss functions for linear regression are convex.
