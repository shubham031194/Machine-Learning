# Linear Regression

## Introduction

Linear Regression is a **supervised machine learning algorithm** primarily used for **regression problems**, where the goal is to predict a continuous output based on one or more input features. The primary task of linear regression is to find the best-fitting straight line that represents the relationship between the input and output data.

---

## Understanding the Problem

Linear regression aims to model the linear relationship between input and output features. Given a training dataset, the model learns to predict an output based on unseen input values.

### Key Terms:
- **Training Dataset**: Data used to train the model.
- **Best-Fit Line**: The straight line that best represents the relationship between input and output features.
- **Residual Error**: The difference between the actual value and the predicted value from the model.

---

## Visual Representation


 ![](https://github.com/shubham031194/Machine-Learning/blob/main/Linear%20Regression/asset/heightvsweightscatterplot.png)

Scatter plot where each point represents pairs of input (e.g., weight) and output features (e.g., height). Linear regression attempts to draw a **best-fit line** through these data points, capturing the trend in the relationship.

 ![](https://github.com/shubham031194/Machine-Learning/blob/main/Linear%20Regression/asset/heightvsweightbestfitlineplot.png)
---

## Mathematical Intuition

The equation of the best-fit line is represented as:

\[
y = mx + c
\]

Where:
- **y** is the predicted output (e.g., height).
- **x** is the input value (e.g., weight).
- **m** is the slope of the line, showing how much **y** changes for a unit change in **x**.
- **c** is the y-intercept, the value of **y** when **x** is 0.

The goal of linear regression is to find the optimal values for **m** and **c** that minimize the **residual error** between the actual and predicted values.

---

## Cost Function

To evaluate how well the line fits the data, we use a **cost function**, which calculates the difference between the predicted and actual values. A common cost function for linear regression is the **Mean Squared Error (MSE)**:

MSE = (1/n) * Σ(yᵢ - ŷᵢ)²

Where:
- n is the number of data points,
- yᵢ is the actual value,
- ŷᵢ is the predicted value.

The goal is to minimize this cost function, thus reducing the prediction error.

---

## Gradient Descent

**Gradient Descent** is an optimization algorithm used to minimize the cost function by adjusting the parameters **m** and **c**. It works by iteratively updating these parameters based on the slope (gradient) of the cost function.

![](https://github.com/shubham031194/Machine-Learning/blob/main/Linear%20Regression/asset/GradientDescent.png)

### Key Concepts:
- **Learning Rate (α)**: Controls the step size during the updates. A small learning rate results in slower but more accurate convergence, while a large learning rate may lead to overshooting the minimum.
- **Convergence**: The process stops when the cost function reaches its global minimum, meaning that the best-fit line has been found.

The gradient descent update rules are:

m = m - α * (∂/∂m) J(m, c)

c = c - α * (∂/∂c) J(m, c)

Where:
- α is the learning rate,
- J(m, c) is the cost function.

![](https://github.com/shubham031194/Machine-Learning/blob/main/Linear%20Regression/asset/LinearRegression_derivation_01.jpg)
---

## Key Takeaways

- Linear regression finds the best-fitting straight line to represent the relationship between input and output features.
- The equation of the line is determined by minimizing the residual error between predicted and actual values.
- **Gradient Descent** is used to optimize the values of **m** and **c** by minimizing the cost function iteratively.
- The **learning rate** plays a crucial role in determining the step size during gradient descent and affects the convergence speed and accuracy.

---


Linear regression is a fundamental algorithm in machine learning, providing an intuitive understanding of relationships between variables. Concepts such as the **cost function**, **gradient descent**, and **learning rate** are key to building, optimizing, and interpreting linear regression models effectively.

---

Happy Learning! 🎉
