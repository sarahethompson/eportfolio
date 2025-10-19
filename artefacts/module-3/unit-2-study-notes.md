[← Back to Unit 2](./)

# Exploratory Data Analysis (EDA) – Study Notes

## What is EDA?
**Exploratory Data Analysis (EDA)** is the **first and most crucial step** in any data science or machine learning project.  
It focuses on **understanding, visualising, and summarising** the main characteristics of a dataset before applying models.

>  *In short: EDA helps you understand your data before you trust your models.*

---

## Objectives of EDA
- Detect **patterns, trends, and relationships** between variables.  
- Identify **missing values**, **outliers**, and **data inconsistencies**.  
- Understand the **distribution** of variables.  
- Generate **hypotheses** and guide **feature engineering**.  
- Provide insights that shape the choice of algorithms and preprocessing methods.

---

## Common EDA Techniques

### 1. **Data Inspection**
- Load and review dataset structure (`.info()`, `.head()`, `.describe()` in pandas).  
- Check data types (categorical, numerical, boolean, datetime).  
- Assess dataset shape (rows × columns) and completeness.

### 2. **Descriptive Statistics**
- Measure **central tendency** – *mean, median, mode*.  
- Measure **spread** – *variance, standard deviation, range, IQR*.  
- Detect **skewness** and **kurtosis** to understand data symmetry.

### 3. **Data Cleaning**
- Handle **missing data** – imputation, deletion, or modelling.  
- Remove or cap **outliers**.  
- Correct **data type mismatches** or **categorical encoding issues**.

### 4. **Univariate Analysis**
Focus on one variable at a time:
- Numerical: histograms, boxplots, density plots.  
- Categorical: bar charts, frequency tables.

### 5. **Bivariate & Multivariate Analysis**
Explore relationships between two or more variables:
- **Numerical–numerical:** scatter plots, correlation matrices, heatmaps.  
- **Categorical–numerical:** boxplots, violin plots, grouped means.  
- **Categorical–categorical:** contingency tables, stacked bar charts.

### 6. **Correlation and Covariance**
- Identify **linear relationships** using *Pearson’s correlation coefficient (r)*.  
- Detect **non-linear patterns** via scatter plot visual inspection.  
- Be mindful: correlation ≠ causation.

---

## Key Visualisation Tools
| Library | Typical Uses |
|----------|---------------|
| **Matplotlib / Seaborn** | General-purpose statistical plotting |
| **Pandas .plot()** | Quick summaries |
| **Plotly / Bokeh** | Interactive dashboards |
| **Sweetviz / Pandas-Profiling / ydata-profiling** | Automated EDA reports |

---

## Example Workflow (Python / Pandas)

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv("data.csv")

# Quick overview
print(df.info())
print(df.describe())

# Missing values
print(df.isnull().sum())

# Univariate analysis
sns.histplot(df["age"], kde=True)
plt.show()

# Bivariate analysis
sns.scatterplot(x="income", y="spending_score", data=df)
plt.show()

# Correlation matrix
sns.heatmap(df.corr(), annot=True, cmap="coolwarm")
plt.show()
```

---

## Common Pitfalls
- Skipping EDA and trusting raw data.  
- Overfitting interpretations (seeing patterns that don’t generalise).  
- Misinterpreting correlation as causation.  
- Ignoring data types or class imbalance.  
- Failing to visualise — numbers alone can be misleading.

---

## Best Practices
- **Visualise early, visualise often.**  
- **Document insights** — note interesting findings and questions.  
- **Iterate** — revisit EDA after feature engineering or modelling.  
- **Compare distributions** between training and test sets.  
- **Automate** repetitive checks using scripts or notebooks.

---

## Summary Table

| Step | Purpose | Example Methods |
|------|----------|-----------------|
| Inspect | Understand data structure | `.head()`, `.info()` |
| Clean | Handle missing/outliers | `.fillna()`, `.dropna()` |
| Explore | Find relationships | `corr()`, scatterplots |
| Visualise | Communicate insights | `matplotlib`, `seaborn` |
| Document | Record findings | Notebook cells, markdown |

---

## Key Takeaway
> EDA bridges **raw data** and **model development** — it’s where intuition meets evidence.  
> Skipping EDA means modelling in the dark.
