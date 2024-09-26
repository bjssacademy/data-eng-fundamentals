## Chapter 3: Aggregating, Grouping, and Merging Data

### Lesson 2: Merging and Joining DataFrames

**Goal of this lesson:**  
In this lesson, you’ll discover how to combine multiple DataFrames in pandas using merging and joining techniques. This is a vital skill in data engineering, especially when dealing with data from different sources.

---

#### Step 1: Combining Data with `merge()`

The **`merge()`** function is used to combine two DataFrames based on a common column or index. This is similar to SQL joins. Here’s a basic example:

```python
import pandas as pd

# Sample data
df1 = pd.DataFrame({
    'EmployeeID': [1, 2, 3],
    'Name': ['Alice', 'Bob', 'Charlie']
})

df2 = pd.DataFrame({
    'EmployeeID': [1, 2, 4],
    'Department': ['Sales', 'Marketing', 'HR']
})

# Merging DataFrames on 'EmployeeID'
merged_df = pd.merge(df1, df2, on='EmployeeID', how='inner')
print(merged_df)
```

In this example, we merge two DataFrames on the **EmployeeID** column using an inner join, meaning only rows with matching **EmployeeID** values will be included.

---

#### Step 2: Understanding Different Types of Joins

You can specify different types of joins in the **`merge()`** function using the **`how`** parameter. Here’s a quick overview of the main types:

- **Inner Join:** Includes only rows with matching values in both DataFrames.
- **Outer Join:** Includes all rows from both DataFrames, filling in NaNs where there are no matches.
- **Left Join:** Includes all rows from the left DataFrame and matching rows from the right DataFrame.
- **Right Join:** Includes all rows from the right DataFrame and matching rows from the left DataFrame.

Here’s how to perform each type of join:

```python
# Outer Join
outer_merged = pd.merge(df1, df2, on='EmployeeID', how='outer')
print(outer_merged)

# Left Join
left_merged = pd.merge(df1, df2, on='EmployeeID', how='left')
print(left_merged)

# Right Join
right_merged = pd.merge(df1, df2, on='EmployeeID', how='right')
print(right_merged)
```

---

#### Step 3: Using `concat()` for Simple Concatenation

Sometimes you just want to stack DataFrames on top of each other or side by side. You can use the **`concat()`** function for this. Here’s an example:

```python
# Sample data
df3 = pd.DataFrame({
    'EmployeeID': [5, 6],
    'Name': ['David', 'Eve']
})

# Concatenating DataFrames vertically
concat_df = pd.concat([df1, df3], ignore_index=True)
print(concat_df)
```

In this case, we concatenate **df1** and **df3** vertically, creating a new DataFrame that includes all employees.

---

#### Step 4: Hands-on Exercise: Joining Two Datasets

Now it’s your turn! Use the following datasets to practise merging and joining:

```python
# Sample datasets
customers = pd.DataFrame({
    'CustomerID': [1, 2, 3],
    'Name': ['Alice', 'Bob', 'Charlie']
})

orders = pd.DataFrame({
    'OrderID': [101, 102, 103],
    'CustomerID': [1, 2, 4],
    'Product': ['A', 'B', 'C']
})

# Exercise 1: Merge customers with orders using an inner join
merged_customers_orders = pd.merge(customers, orders, on='CustomerID', how='inner')
print(merged_customers_orders)

# Exercise 2: Merge using an outer join to include all customers and orders
outer_merged_customers_orders = pd.merge(customers, orders, on='CustomerID', how='outer')
print(outer_merged_customers_orders)

# Exercise 3: Use concat to combine the two DataFrames in a different way if you wish
```

---

#### Summary

In this lesson, we’ve covered:
- How to combine DataFrames using the **`merge()`** function.
- Different types of joins (inner, outer, left, right).
- Using **`concat()`** for simple concatenation of DataFrames.
- Hands-on exercises to practise merging customer and order datasets.


---
[>> Next Lesson](./chapter3-3.md)