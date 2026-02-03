# Python for Data Analysts: A Comprehensive Guide

Become a data expert! This course focuses on the "Big Three" libraries of the Python data ecosystem: NumPy, Pandas, and Matplotlib.

---

## 1. Prerequisites Refresh
Before starting, ensure you are comfortable with List Comprehensions and Dictionaries.
```python
# List comprehension: create a list of squares
squares = [x**2 for x in range(10)]
```

---

## 2. Numerical Computing with NumPy
NumPy is the foundation of numerical computing in Python. It provides the `ndarray` object, which is much faster than standard Python lists.

### Creating Arrays
```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])
zeros = np.zeros((3, 3))    # 3x3 matrix of zeros
range_arr = np.arange(0, 10, 2)
```

### Array Operations & Broadcasting
NumPy allows you to perform operations on whole arrays without loops.
```python
data = np.array([1, 2, 3])
result = data * 2      # [2, 4, 6]
```

---

## 3. Data Manipulation with Pandas
Pandas is built on NumPy and provides the `DataFrame` structure, which is like a SQL table or Excel sheet.

### Loading and Exploring Data
```python
import pandas as pd

df = pd.read_csv('data.csv')
print(df.head())        # View first 5 rows
print(df.info())        # Column types and non-null counts
print(df.describe())    # Statistical summary
```

### Data Cleaning
```python
df.dropna()                            # Remove missing values
df.fillna(0)                           # Replace missing with 0
df.drop_duplicates(inplace=True)
df['column'] = df['column'].astype(int) # Change type
```

### Grouping and Aggregating
```python
city_sales = df.groupby('City')['Sales'].sum()
```

---

## 4. Data Visualization
Visualizing data is key to understanding patterns.

### Matplotlib Basics
```python
import matplotlib.pyplot as plt

plt.plot([1, 2, 3], [4, 5, 6])
plt.title("Line Chart")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.show()
```

### Statistical Plots with Seaborn
```python
import seaborn as sns

# Load a built-in dataset
tips = sns.load_dataset("tips")
sns.scatterplot(data=tips, x="total_bill", y="tip", hue="time")
plt.show()
```

---

## 5. Statistical Analysis
Python makes it easy to perform statistical tests.
```python
from scipy import stats

data1 = [20, 21, 19, 22, 18]
data2 = [28, 30, 27, 29, 31]
t_stat, p_val = stats.ttest_ind(data1, data2)
print(f"P-value: {p_val}") # If < 0.05, results are significant
```

---

## 6. Capstone Project Workflow: Exploratory Data Analysis (EDA)
A typical EDA workflow involves:
1.  **Data Loading**: Importing the dataset.
2.  **Cleaning**: Handling nulls, outliers, and incorrect formats.
3.  **Visualization**: Plotting distributions and correlations.
4.  **Reporting**: Summarizing findings with clear charts.

---
[Return to Main README](README.md)
