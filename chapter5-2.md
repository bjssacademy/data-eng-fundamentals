## Chapter 5: Advanced Techniques in NumPy and pandas for Data Engineering

### Lesson 2: Applying Functions with pandas (`apply()` and `map()`)

**Goal of this lesson:**  
In this lesson, you'll learn how to apply functions to your DataFrames using pandas. This is vital for transforming data and performing custom operations efficiently.

---

#### Step 1: Using `apply()`, `map()`, and `applymap()` for Transformation

pandas provides powerful methods for applying functions to DataFrames and Series. 

- **`apply()`** is used to apply a function along a specific axis (rows or columns) of a DataFrame or to a Series.
- **`map()`** is primarily used for transforming values in a Series.
- **`applymap()`** is used to apply a function element-wise across an entire DataFrame.

**Example of `apply()`:**

```python
import pandas as pd

# Create a sample DataFrame
df = pd.DataFrame({
    'A': [1, 2, 3],
    'B': [4, 5, 6]
})

# Applying a function to each column
df['C'] = df['A'].apply(lambda x: x ** 2)
print(df)
```

**Example of `map()`:**

```python
# Using map to transform values in a Series
df['D'] = df['B'].map(lambda x: x * 10)
print(df)
```

**Example of `applymap()`:**

```python
# Applying a function element-wise to the entire DataFrame
df = df.applymap(lambda x: x + 1)
print(df)
```

---

#### Step 2: Lambda Functions and Custom Transformations

Lambda functions are anonymous functions that are defined using the `lambda` keyword. They are useful for quick, throwaway functions.

**Example of a Lambda Function:**

```python
# Create a Series
series = pd.Series([1, 2, 3, 4])

# Apply a lambda function
result = series.apply(lambda x: x * 2)
print(result)
```

You can also define your own custom functions for more complex operations.

**Example of a Custom Function:**

```python
def custom_function(x):
    return x ** 3 + 1

# Apply custom function to a Series
result_custom = series.apply(custom_function)
print(result_custom)
```

---

#### Step 3: Hands-on Exercise: Apply Custom Functions Across DataFrame Columns

Now it’s your turn to practise applying functions! Follow these steps:

1. **Create a DataFrame** with some sample data.
  
   ```python
   data = {
       'name': ['Alice', 'Bob', 'Charlie'],
       'age': [24, 30, 22],
       'salary': [50000, 60000, 55000]
   }
   df = pd.DataFrame(data)
   ```

2. **Apply a function to transform the age** into a decade (e.g., 20s, 30s).
  
   ```python
   def age_group(age):
       if age < 30:
           return '20s'
       else:
           return '30s'

   df['age_group'] = df['age'].apply(age_group)
   print(df)
   ```

3. **Use `map()` to increase salary** by 10% for everyone.
  
   ```python
   df['salary'] = df['salary'].map(lambda x: x * 1.10)
   print(df)
   ```

4. **Use `applymap()` to add a prefix** to all names in the DataFrame.
  
   ```python
   df[['name']] = df[['name']].applymap(lambda x: f'Ms. {x}' if 'Alice' in x else f'Mr. {x}')
   print(df)
   ```

---

#### Summary

In this lesson, we've covered:
- How to use `apply()`, `map()`, and `applymap()` for data transformation in pandas.
- The use of lambda functions for quick transformations.
- A hands-on exercise to apply custom functions across DataFrame columns.

---
[>> Next Lesson](./chapter5-3.md)