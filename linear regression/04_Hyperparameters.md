# Tuning Hyperparameters in Linear Regression

## Table of Contents
1. [What are Hyperparameters?](#what-are-hyperparameters)
2. [Learning Rate](#learning-rate)
3. [Epochs](#epochs)
4. [Batch Size](#batch-size)
5. [Key Terms](#key-terms)

---

## What are Hyperparameters?
**Hyperparameters** are the configuration settings that are used to control the training process of a machine learning model. Unlike **parameters** (the weights and bias), which are learned automatically from the data, hyperparameters are set by the programmer *before* training begins. Tuning them is crucial for efficient and effective training.

## Learning Rate
The **learning rate** is arguably the most important hyperparameter. It controls the size of the step that gradient descent takes during each iteration when updating the model's weights and bias.

-   **Too low of a learning rate:** Training will be very slow and may take an excessive number of iterations to converge.
-   **Too high of a learning rate:** The algorithm may "overshoot" the minimum of the loss curve and fail to converge, as it bounces back and forth across the optimal point.

Finding the "Goldilocks" learning rate (not too high, not too low) is key to minimizing loss efficiently. This is often found through experimentation.

## Epochs
An **epoch** represents one full pass of the training algorithm over the *entire* training dataset. The number of epochs determines how many times the model gets to see and learn from the full set of training data.

-   **Too few epochs:** The model may not have had enough time to learn the underlying patterns, a state known as **underfitting**.
-   **Too many epochs:** The model might start to memorize the training data, including its noise, and perform poorly on new, unseen data. This is called **overfitting**.

The ideal number of epochs is often determined by observing the loss curve and stopping when the loss plateaus.

## Batch Size
The **batch size** defines the number of examples from the training dataset that are used to calculate the gradient in a single iteration.

-   **Full-batch (or Batch Gradient Descent):** The batch size is equal to the entire training dataset. This can be computationally expensive and slow for large datasets.
-   **Stochastic Gradient Descent (SGD):** The batch size is 1. The model updates its parameters after every single example. This is computationally efficient but can result in a "noisy" or unstable training process, as the gradient can fluctuate wildly.
-   **Mini-batch Gradient Descent:** The batch size is a value between 1 and the total number of examples (commonly 32, 64, 128, etc.). This is the most common approach as it provides a balance between the computational efficiency of SGD and the stability of full-batch training.

## Key Terms
- **Hyperparameter**: A configuration that is set by the programmer to control the training process.
- **Parameter**: The internal variables of the model (weights and bias) that are learned from the data.
- **Learning Rate**: The step size used by gradient descent to update the model's parameters.
- **Epoch**: One full pass through the entire training dataset.
- **Batch Size**: The number of training examples used in one iteration to calculate the gradient.
- **Stochastic Gradient Descent (SGD)**: A training method with a batch size of 1.
- **Mini-batch Gradient Descent**: A training method that uses a small, random subset of the data for each update.
