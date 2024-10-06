# Cost Functions

This section talks on diffrent cost functions that can be used to optimize the machine learning algorithms.

---

### **Mean Squared Error (MSE)**
MSE calculates the average of the squared differences between the predicted and actual values. It is widely used due to its simplicity and usefulness in optimization.

![image](https://github.com/user-attachments/assets/8ffa070b-0566-4e67-97c4-d35776c4baf4)

Where:
![image](https://github.com/user-attachments/assets/3907485c-7072-49ba-a1e9-064e2abb6da2) : Actual value
![image](https://github.com/user-attachments/assets/d14d69eb-d5ce-4274-9d1d-738704f9a4b1) : Predicted value
n : Number of Observations

**Advantages:**
1. Differentiability: MSE is fully differentiable, which means its derivative can be calculated at any point. This allows gradient descent algorithms to easily minimize MSE by finding the global minimum.
2. Global Minimum: MSE has only one local minimum, which is also the global minimum. Gradient descent will always converge to the global minimum, regardless of the starting point.

**Disadvantages:**
1. Sensitivity to Outliers: Since MSE squares the errors, larger errors (often caused by outliers) have a disproportionate impact. This can skew the best-fit line.
2. Units: MSE changes the units of the output variable (e.g., if the variable is in dollars, MSE will be in dollars squared), making it harder to interpret.

---

### **Mean Absolute Error (MAE)**
MAE calculates the average of the absolute differences between the predicted and actual values. Unlike MSE, it focuses on the magnitude of the error, ignoring whether the error is positive or negative.

![image](https://github.com/user-attachments/assets/cc39c551-8bfb-4eb1-a58a-8cb4e8418d55)

**Advantages:**
1. Robust to Outliers: MAE gives equal weight to all errors by using absolute differences. This makes it less sensitive to outliers compared to MSE, which squares the errors.
2. Interpretability: The units of MAE are the same as the units of the output variable, making it more interpretable.

**Disadvantages:**
1. Non-Differentiability: MAE is not differentiable at zero, meaning subgradient methods must be used to find the minimum, which can slow down convergence.
2. Multiple Local Minima: Optimization with MAE can be non-convex, meaning there can be multiple local minima. This makes it harder for gradient descent to consistently find the global minimum.

---

### **Root Mean Squared Error (RMSE)**
RMSE is the square root of the MSE. It is often used when the errors need to be expressed in the same units as the output variable.
![image](https://github.com/user-attachments/assets/e23fec68-9f6d-46c4-add9-a3ca9f8a688a)

**Advantages:**
1. Units: RMSE resolves the unit issue found in MSE by taking the square root, ensuring that the error is measured in the same units as the output variable.
2. Balance: RMSE balances the benefits of both MSE and MAE, as it still penalizes larger errors but less severely than MSE.

**Disadvantages:**
1. Similar to MSE, RMSE can still be influenced by outliers, although to a slightly lesser extent due to the square root operation.

---

**Notes:**
1. MSE is preferable when minimizing large errors is crucial and when you want to take advantage of gradient-based optimization techniques.
2. MAE is ideal when robustness to outliers is needed and when interpretability of the error metric is important.
3. RMSE is a middle ground, offering an interpretable error measure that still penalizes larger errors more than MAE.

---

Happy Learning! 🎉
