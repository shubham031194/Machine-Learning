# **Logistic Regression**
Logistic Regression is a supervised machine learning algorithm primarily used for classification tasks, specifically binary classification problems. It predicts the probability of an input belonging to one of two categories, typically denoted as class 0 or class 1.

While both Logistic Regression and Linear Regression are forms of regression, they serve different purposes:
1. **Linear Regression:** Predicts a continuous output based on input variables. It is used for regression tasks where the dependent variable is continuous, such as predicting house prices.
2. **Logistic Regression:** Predicts the probability of a class label (often binary) based on input variables. It is used for classification tasks where the dependent variable is categorical, such as determining whether an email is spam or not.
The distinction lies in the output: Logistic Regression outputs a probability value between 0 and 1, while Linear Regression gives a continuous number, which could be anything between negative and positive infinity. This distinction is key for classification tasks.

### **Why Not Use Linear Regression for Classification?**
When trying to solve classification problems with Linear Regression, some key issues arise:
1. **Outliers:** Linear regression is sensitive to outliers, which can lead to predictions outside the bounds of valid probabilities (i.e., less than 0 or greater than 1), which is not useful for classification.
2. **Boundaries:** Linear regression does not have a mechanism to produce a probability-like output, as probabilities are naturally bounded between 0 and 1. Without transformation, the continuous output is not interpretable for classification.

This is where Logistic Regression comes in, using a sigmoid function to map outputs into a valid probability range.

## **Sigmoid Function: The Core of Logistic Regression**
The sigmoid function is a mathematical transformation used to map any real-valued number into a value between 0 and 1. This is essential for logistic regression because we need outputs that represent probabilities.

The sigmoid function is given by:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Logistic%20Regression/assets/logistic_sigmoid.jpg)

Where:

* x is the linear combination of input features and weights (i.e.,  ![](https://github.com/shubham031194/Machine-Learning/blob/main/Logistic%20Regression/assets/logistic_input.jpg) ).
* e is the mathematical constant Euler’s number (𝑒 ≈ 2.718).

This function has two important properties:
1. The output is bounded between 0 and 1, making it suitable for probabilities.
2. The function is S-shaped (sigmoidal), meaning small negative inputs will result in values close to 0, while large positive inputs will result in values close to 1.\

## **Decision Rule in Logistic Regression:**

Once the sigmoid function produces a probability, we can classify the output based on a threshold (commonly 0.5):
* If the probability 𝑃 ≥ 0.5, classify the input as class 1.
* If the probability 𝑃 < 0.5, classify the input as class 0.

## **Hypothesis in Logistic Regression**
In Linear Regression, the hypothesis is represented as a linear equation:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Logistic%20Regression/assets/logistic_linera_equation.jpg)

This equation directly predicts the output. In Logistic Regression, we modify this hypothesis by applying the sigmoid function to the linear combination of inputs. The hypothesis becomes:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Logistic%20Regression/assets/logistic_hypothesis.jpg)

Where 𝜎 is the sigmoid function. This modification ensures the output is a probability value.

## **Cost Function in Logistic Regression**
In Linear Regression, the cost function is the mean squared error (MSE), which is a convex function. However, for Logistic Regression, MSE is not suitable because:
1. The sigmoid function introduces non-linearity, and MSE would lead to a non-convex cost function, which makes optimization harder.
2. Squared error penalizes large errors disproportionately, which can be problematic in classification.

Instead, Logistic Regression uses a cost function derived from the concept of log-likelihood. The cost function for a single training example is:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Logistic%20Regression/assets/logistic_log_likelihood.jpg)

For a dataset with multiple training examples, we sum the costs over all examples. The final cost function (for the entire dataset) is:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Logistic%20Regression/assets/logistict_cost_func.jpg)

Where:

* m is the number of training examples.
* h(x(𝑖)) is the predicted probability for the 𝑖-th example.
* y (i) is the actual class label (0 or 1) for the 𝑖-th example.

This cost function is convex, which ensures that gradient descent can find the global minimum efficiently.

## **Gradient Descent for Optimization**
Gradient Descent is an optimization technique used to minimize the cost function. In Logistic Regression, the weights 𝜃 are updated iteratively to minimize the cost function using the gradient of the cost function.

The update rule for gradient descent is:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Logistic%20Regression/assets/Logistic_update_weights.jpg)

Where:

* η is the learning rate, controlling the step size.
* ∂J(θ) / ∂θj​ is the partial derivative of the cost function with respect to 𝜃𝑗, indicating the direction in which the cost function decreases most rapidly.

The gradients of the cost function for Logistic Regression can be derived as:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Logistic%20Regression/assets/Logistic_gradients.jpg)

Note:

When we have more than two classes in a classification problem, we move beyond binary classification and require techniques that extend Logistic Regression to handle multiclass classification. The two main approaches used for this are:
1. One-vs-Rest (OvR) or One-vs-All (OvA)
2. Softmax Regression (Multinomial Logistic Regression)
Happy Learning! 🎉
