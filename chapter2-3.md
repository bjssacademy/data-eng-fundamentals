## Chapter 2: Data Manipulation with pandas and NumPy

### Lesson 3: Data Cleaning and Transformation with pandas

**Goal of this lesson:**  
In this lesson, you’ll learn how to clean and transform data in pandas. This is essential for data engineering, as raw data is often messy and needs to be shaped for analysis or pipelines.

---

#### Step 1: Handling Missing Data

Missing data is common in real-world datasets. **pandas** offers several methods for dealing with missing values, such as **`dropna()`** and **`fillna()`**.

1. **Removing rows with missing values:**

Let’s create a DataFrame with some missing data:

```python
import pandas as pd
import numpy as np

data = {
    'Name': ['Alice', 'Bob', 'Charlie', np.nan],
    'Age': [25, np.nan, 37, 29],
    'City': ['London', 'Manchester', np.nan, 'Liverpool']
}

df = pd.DataFrame(data)

# Drop rows with missing values
df_cleaned = df.dropna()
print(df_cleaned)
```

2. **Filling missing values:**

Instead of dropping rows, you might want to fill the missing values with something more meaningful, like the average of a column:

```python
# Fill missing values in 'Age' with the mean of the column
df['Age'] = df['Age'].fillna(df['Age'].mean())
print(df)
```

---

#### Step 2: Renaming and Dropping Columns

Sometimes you need to rename columns to make the data more readable or drop unnecessary columns.

1. **Renaming columns:**

```python
# Rename 'Name' to 'Full Name' and 'Age' to 'Years'
df = df.rename(columns={'Name': 'Full Name', 'Age': 'Years'})
print(df)
```

2. **Dropping columns:**

```python
# Drop the 'City' column
df = df.drop(columns=['City'])
print(df)
```

---

#### Step 3: Replacing Values

You may also need to replace specific values in your data. For example, let’s replace all instances of `'Bob'` with `'Robert'`:

```python
# Replace 'Bob' with 'Robert'
df['Full Name'] = df['Full Name'].replace('Bob', 'Robert')
print(df)
```

---

#### Step 4: Hands-on Exercise: Cleaning a Raw Dataset

Now, let’s clean a raw dataset together. You can use this sample dataset:

```python
data = {
    'Name': ['Alice', 'Bob', 'Charlie', np.nan, 'Eve'],
    'Age': [25, np.nan, 37, 29, np.nan],
    'Salary': [50000, 60000, np.nan, 45000, 70000]
}

df = pd.DataFrame(data)

# Exercise 1: Fill missing 'Age' values with the mean of the 'Age' column
df['Age'] = df['Age'].fillna(df['Age'].mean())
print(df)

# Exercise 2: Replace missing 'Salary' values with 0
df['Salary'] = df['Salary'].fillna(0)
print(df)

# Exercise 3: Rename 'Salary' to 'Annual Income'
df = df.rename(columns={'Salary': 'Annual Income'})
print(df)

# Add more cleaning tasks based on what you notice!
```

---

#### Summary

In this lesson, we’ve covered:
- How to handle missing data with **`dropna()`** and **`fillna()`**.
- Renaming and dropping columns.
- Replacing values within a DataFrame.
- Hands-on exercises to practice cleaning and transforming data.


---
[>> Next Lesson](./chapter2-4.md)