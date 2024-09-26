## Chapter 2: Data Manipulation with pandas and NumPy

### Lesson 2: NumPy Arrays for Performance Optimization

**Goal of this lesson:**  
In this lesson, you’ll learn why **NumPy** arrays are faster than regular pandas operations and how to use them to optimise performance in data engineering tasks.

---

#### Step 1: Why Use NumPy Arrays?

**NumPy** is a powerful library for numerical computing in Python. While **pandas** builds on top of **NumPy**, pandas DataFrames are more flexible and come with some overhead. When you’re dealing with huge datasets, **NumPy** can help speed things up.

NumPy arrays:
- Take up less memory.
- Are faster because they avoid some of the abstraction pandas adds.

---

#### Step 2: Creating a NumPy Array

Let’s create a simple NumPy array and compare it to a pandas Series:

```python
import numpy as np
import pandas as pd
import time

# Create a NumPy array of 1 million elements
arr = np.random.rand(1_000_000)

# Create a pandas Series of 1 million elements
series = pd.Series(arr)

# Compare performance of summing the elements
start_time = time.time()
np_sum = np.sum(arr)
print(f"NumPy sum: {np_sum}, Time: {time.time() - start_time:.5f} seconds")

start_time = time.time()
pd_sum = series.sum()
print(f"pandas sum: {pd_sum}, Time: {time.time() - start_time:.5f} seconds")
```

You’ll notice that NumPy performs this operation faster.

---

#### Step 3: Using `numpy.where()` for Conditional Operations

Sometimes you need to apply conditional logic to your data. You can use **`numpy.where()`** to efficiently replace or create values based on a condition.

Here’s how you’d do it with **pandas**, then with **NumPy**:

```python
# Using pandas to apply a condition
df = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie', 'David'],
    'Age': [25, 32, 37, 29]
})

# Create a new column where age > 30 is labelled 'Older', otherwise 'Younger'
df['Category'] = df['Age'].apply(lambda x: 'Older' if x > 30 else 'Younger')
print(df)

# Using NumPy for the same operation
df['Category'] = np.where(df['Age'] > 30, 'Older', 'Younger')
print(df)
```

Using **`numpy.where()`** is faster for larger datasets because it works directly with arrays, avoiding some of the overhead that comes with pandas’ `.apply()` function.

---

#### Step 4: Hands-on Exercise: Using NumPy to Optimise pandas Operations

Now, let’s try optimising some operations on a larger dataset:

```python
# Create a large DataFrame with random data
df_large = pd.DataFrame({
    'A': np.random.rand(1_000_000),
    'B': np.random.rand(1_000_000)
})

# Exercise 1: Add a new column 'C' where 'A' > 0.5 is True, else False (first with pandas)
start_time = time.time()
df_large['C'] = df_large['A'].apply(lambda x: True if x > 0.5 else False)
print(f"pandas apply time: {time.time() - start_time:.5f} seconds")

# Exercise 2: Optimise the same operation using NumPy
start_time = time.time()
df_large['C'] = np.where(df_large['A'] > 0.5, True, False)
print(f"NumPy where time: {time.time() - start_time:.5f} seconds")
```

---

#### Summary

In this lesson, we’ve covered:
- Why **NumPy** is useful for performance optimisation in data engineering.
- How to create and use **NumPy arrays**.
- Using **`numpy.where()`** to speed up conditional logic.
- Hands-on exercises to practice optimising **pandas** operations with **NumPy**.



---
[>> Next Lesson](./chapter2-3.md)