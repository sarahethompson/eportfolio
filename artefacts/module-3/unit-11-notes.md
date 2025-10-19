[← Back to Unit 11](./)

# Model Selection and Evaluation – Study Notes

## 1. Overview
- Model selection and evaluation are essential steps in the machine learning process.  
- They ensure that the chosen model performs accurately, efficiently, and generalises well to unseen data.  
- The aim is not just to achieve high accuracy on training data but to build models that perform well on new, unseen examples.

---

## 2. Key Concepts

| Term | Description |
|------|--------------|
| Model Selection | Choosing the best algorithm and configuration for a task. |
| Model Evaluation | Assessing how well a trained model performs. |
| Generalisation | The model’s ability to perform well on unseen data. |
| Overfitting | When a model learns noise or patterns specific to training data and performs poorly on new data. |
| Underfitting | When a model is too simple and fails to capture key patterns in the data. |

---

## 3. The Model Evaluation Process
1. Split the data – typically into training, validation, and test sets.  
2. Train models – using the training data.  
3. Validate – tune hyperparameters and compare model performance on the validation set.  
4. Test – evaluate the final chosen model on unseen test data.  
5. Select – the model with the best balance between bias and variance.

---

## 4. Evaluation Metrics

### Classification Metrics

| Metric | Description |
|---------|--------------|
| Accuracy | Proportion of correctly predicted samples. |
| Precision | Proportion of positive predictions that are correct. |
| Recall (Sensitivity) | Proportion of actual positives correctly identified. |
| F1 Score | Harmonic mean of precision and recall. |
| ROC Curve / AUC | Measures trade-off between true positive and false positive rates. |

### Regression Metrics

| Metric | Description |
|---------|--------------|
| Mean Absolute Error (MAE) | Average of absolute differences between predicted and actual values. |
| Mean Squared Error (MSE) | Average of squared differences; penalises large errors. |
| Root Mean Squared Error (RMSE) | Square root of MSE, interpretable in original units. |
| R² (Coefficient of Determination) | Measures how much variance in target variable is explained by the model. |

---

## 5. Cross-Validation
- A robust method to assess model performance and generalisation.  
- k-Fold Cross-Validation:
  1. Split data into k subsets (folds).  
  2. Train on k-1 folds and test on the remaining one.  
  3. Repeat k times, each time using a different test fold.  
  4. Average the scores to estimate performance.

**Advantages:**
- Reduces bias due to random data splits.  
- Provides a more stable estimate of model performance.

---

## 6. Model Selection Techniques

### 1. Hold-Out Method
- Split data into training/validation/test sets.  
- Simple but performance may vary depending on the split.

### 2. Cross-Validation (Preferred)
- Provides a more reliable estimate of performance across multiple folds.

### 3. Grid Search / Random Search
- Grid Search: systematically tests combinations of hyperparameters.  
- Random Search: samples random combinations (more efficient for large parameter spaces).

### 4. Automated Model Selection
- Tools like AutoML, Optuna, or Bayesian optimisation automatically explore algorithms and hyperparameters.

---

## 7. Hyperparameter Tuning
- Hyperparameters are model settings not learned from data (e.g., learning rate, number of layers, regularisation strength).  
- Tuning aims to find the combination that maximises model performance.  
- Techniques:
  - Grid Search  
  - Random Search  
  - Bayesian Optimisation  
  - Cross-Validation for evaluation

---

## 8. Preventing Overfitting
- Regularisation: Add penalties to large weights (L1/L2 regularisation).  
- Dropout: Randomly remove neurons during training (for neural networks).  
- Early Stopping: Stop training when validation performance stops improving.  
- Data Augmentation: Increase dataset variability (especially in images).  
- Cross-Validation: Ensures generalisable performance.

---

## 9. Model Comparison
- Compare models using the same data splits and evaluation metrics.  
- Use validation scores, training time, and interpretability to decide.  
- Avoid using the test set until final evaluation.

---

## 10. Example in Python (Classification)

```python
from sklearn.model_selection import train_test_split, cross_val_score, GridSearchCV
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report, accuracy_score
import pandas as pd

# Load data
df = pd.read_csv("data.csv")
X = df.drop("target", axis=1)
y = df["target"]

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Model
model = RandomForestClassifier(random_state=42)
model.fit(X_train, y_train)

# Evaluate
y_pred = model.predict(X_test)
print("Accuracy:", accuracy_score(y_test, y_pred))
print(classification_report(y_test, y_pred))
```

---

## 11. Bias-Variance Trade-Off
- Bias: Error due to overly simplistic models (underfitting).  
- Variance: Error due to overly complex models (overfitting).  
- The goal is to find the optimal balance that minimises total error.

---

## 12. Best Practices
- Always use train/test splits or cross-validation.  
- Compare multiple models using consistent metrics.  
- Tune hyperparameters with validation data only.  
- Avoid data leakage (do not use test data in training).  
- Track and document all results for reproducibility.

---

## 13. Summary Table

| Step | Purpose | Example Tools |
|------|----------|----------------|
| Data Split | Separate training/validation/test sets | train_test_split() |
| Evaluation | Assess model accuracy and generalisation | classification_report, r2_score |
| Cross-Validation | Reliable performance estimate | cross_val_score() |
| Hyperparameter Tuning | Optimise performance | GridSearchCV, RandomizedSearchCV |
| Final Testing | Confirm performance on unseen data | Test set evaluation |
