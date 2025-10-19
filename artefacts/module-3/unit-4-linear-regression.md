[← Back to Unit 4](./)

# Linear Regression with Scikit-Learn – Study Notes

## What is Linear Regression
Linear Regression is a supervised learning algorithm used to model the relationship between a dependent variable (target) and one or more independent variables (features).  
It assumes a linear relationship:

y = a + b1x1 + b2x2 + ... + bnxn

where:  
- y = predicted output  
- a = intercept  
- b1...bn = coefficients (weights) for each feature  
- x1...xn = input features  

---

## Goal
To find the best-fit line (or hyperplane) that minimises the error between predicted and actual values — usually via the Ordinary Least Squares (OLS) method.

---

## Key Concepts

| Concept | Description |
|----------|-------------|
| Dependent variable (y) | The value we are predicting |
| Independent variable(s) (X) | Input data/features used to make predictions |
| Intercept | The constant value where the line crosses the y-axis |
| Coefficient(s) | Represent the strength and direction of each feature’s influence |
| Residuals | Differences between actual and predicted values |
| R² (R-squared) | Explains how much of the variance in y is explained by X |

---

## Example in Scikit-Learn

```python
# 1. Import libraries
import numpy as np
import pandas as pd
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score

# 2. Load dataset (example)
df = pd.read_csv("data.csv")

# 3. Define features (X) and target (y)
X = df[["feature1", "feature2"]]  # independent variables
y = df["target"]                   # dependent variable

# 4. Split data into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# 5. Create and train model
model = LinearRegression()
model.fit(X_train, y_train)

# 6. Make predictions
y_pred = model.predict(X_test)

# 7. Evaluate model
print("Intercept:", model.intercept_)
print("Coefficients:", model.coef_)
print("Mean Squared Error:", mean_squared_error(y_test, y_pred))
print("R² Score:", r2_score(y_test, y_pred))
```

---

## Visualising the Regression Line

```python
import matplotlib.pyplot as plt

plt.scatter(X_test["feature1"], y_test, color='blue', label="Actual")
plt.plot(X_test["feature1"], y_pred, color='red', label="Predicted Line")
plt.xlabel("Feature 1")
plt.ylabel("Target")
plt.legend()
plt.show()
```

---

## Evaluation Metrics

| Metric | Description |
|---------|--------------|
| Mean Absolute Error (MAE) | Average of absolute differences between predicted and actual values |
| Mean Squared Error (MSE) | Average of squared differences (penalises large errors) |
| Root Mean Squared Error (RMSE) | Square root of MSE – interpretable in original units |
| R² Score | Proportion of variance explained (closer to 1 = better fit) |

---

## Assumptions of Linear Regression
1. Linearity – Relationship between X and y is linear.  
2. Independence – Observations are independent of each other.  
3. Homoscedasticity – Equal variance of residuals.  
4. Normality – Residuals are normally distributed.  
5. No multicollinearity – Features are not highly correlated with each other.

---

## Tips and Best Practices
- Scale data if features vary greatly in magnitude.  
- Check correlations before applying regression.  
- Use train/test split or cross-validation to avoid overfitting.  
- If the relationship is not linear, consider:
  - Polynomial Regression  
  - Regularised models (Ridge, Lasso, ElasticNet)

---

## Summary

| Step | Description |
|------|--------------|
| 1 | Import libraries and load data |
| 2 | Define X (features) and y (target) |
| 3 | Split data into train/test sets |
| 4 | Train LinearRegression model |
| 5 | Predict and evaluate performance |
| 6 | Visualise and interpret results |
