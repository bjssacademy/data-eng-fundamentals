## Chapter 4: Data Engineering Pipelines with pandas

### Lesson 3: Handling Data Quality Issues

**Goal of this lesson:**  
In this lesson, you'll learn how to identify and handle data quality issues that can arise during data engineering tasks. Ensuring data quality is crucial for reliable analysis and decision-making.

---

#### Step 1: Identifying Duplicates

Duplicates can skew your analysis and lead to incorrect conclusions. Here’s how to identify and handle them using pandas.

**Finding Duplicates**

```python
import pandas as pd

# Load the data
data = pd.read_csv('customer_data.csv')

# Identify duplicates
duplicates = data[data.duplicated()]
print(f'Duplicate rows:\n{duplicates}')
```

**Removing Duplicates**

```python
# Remove duplicates
data_cleaned = data.drop_duplicates()
print(f'Cleaned data:\n{data_cleaned.head()}')
```

---

#### Step 2: Handling Missing Values

Missing data is a common issue that needs to be addressed before analysis. You have several options for handling missing values, such as dropping them or filling them with specific values.

**Identifying Missing Values**

```python
# Check for missing values
missing_values = data.isnull().sum()
print(f'Missing values in each column:\n{missing_values}')
```

**Dropping Missing Values**

```python
# Drop rows with any missing values
data_dropped = data.dropna()
```

**Filling Missing Values**

```python
# Fill missing values with a specific value
data_filled = data.fillna(value={'Age': 0, 'City': 'Unknown'})
```

---

#### Step 3: Data Validation and Constraints

Data validation helps ensure that the data meets specific criteria or constraints. This can involve checking for valid ranges or formats.

**Example: Validating Age**

```python
# Check for valid ages (e.g., between 0 and 120)
invalid_age = data[(data['Age'] < 0) | (data['Age'] > 120)]
print(f'Invalid ages:\n{invalid_age}')
```

**Example: Enforcing Constraints**

If you find invalid data, you can either remove it or correct it based on your business rules.

```python
# Removing invalid ages
data_validated = data[(data['Age'] >= 0) & (data['Age'] <= 120)]
```

---

#### Step 4: Hands-on Exercise: Detect and Fix Quality Issues in a Dataset

Now it’s your turn to practise handling data quality issues! Follow these steps:

1. **Load a dataset** named **`[raw_employee_data.csv](./resources/raw_employee_data.csv)`** and display the first few rows.
  
   ```python
   employee_data = pd.read_csv('raw_employee_data.csv')
   print(employee_data.head())
   ```

2. **Identify and handle duplicates** in the dataset.
  
   ```python
   duplicates = employee_data[employee_data.duplicated()]
   print(f'Duplicates found:\n{duplicates}')
   employee_data = employee_data.drop_duplicates()
   ```

3. **Check for missing values** and decide how to handle them (drop or fill).
  
   ```python
   missing_values = employee_data.isnull().sum()
   print(f'Missing values in each column:\n{missing_values}')
   employee_data = employee_data.fillna(value={'Department': 'Unknown'})
   ```

4. **Validate the data** for any specific business rules, such as checking the range of employee ages.
  
   ```python
   invalid_age = employee_data[(employee_data['Age'] < 0) | (employee_data['Age'] > 120)]
   print(f'Invalid ages:\n{invalid_age}')
   employee_data = employee_data[(employee_data['Age'] >= 0) & (employee_data['Age'] <= 120)]
   ```

5. **Save the cleaned dataset** as **`cleaned_employee_data.csv`**.

   ```python
   employee_data.to_csv('cleaned_employee_data.csv', index=False)
   print('Cleaned employee data saved to cleaned_employee_data.csv')
   ```

---

#### Summary

In this lesson, we've covered:
- How to identify and handle duplicates in a dataset.
- Strategies for dealing with missing values.
- The importance of data validation and enforcing constraints.
- A hands-on exercise to practise detecting and fixing quality issues in a dataset.

---
[>> Next Lesson](./chapter5-1.md)