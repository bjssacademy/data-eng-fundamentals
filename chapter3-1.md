## Chapter 3: Aggregating, Grouping, and Merging Data

### Lesson 1: Aggregation and GroupBy

**Goal of this lesson:**  
In this lesson, you’ll learn how to use the **`groupby()`** function in pandas to effectively aggregate data. This is a crucial skill for summarising and analysing datasets in data engineering.

---

#### Step 1: Understanding the `groupby()` Function

The **`groupby()`** function is a powerful feature that allows you to group data based on one or more columns. Once grouped, you can apply various aggregation functions to summarise the data.

Here’s a simple example to illustrate:

```python
import pandas as pd

# Sample data
data = {
    'Region': ['North', 'South', 'East', 'West', 'North', 'South'],
    'Sales': [150, 200, 100, 180, 220, 210],
    'Product': ['A', 'B', 'A', 'B', 'A', 'B']
}

df = pd.DataFrame(data)

# Group by 'Region' and calculate the total 'Sales'
grouped_sales = df.groupby('Region')['Sales'].sum()
print(grouped_sales)
```

In this example, we group the data by the **Region** column and sum the **Sales** for each region.

---

#### Step 2: Aggregating Data Using `sum()`, `mean()`, and `count()`

You can apply several aggregation functions like **`sum()`**, **`mean()`**, and **`count()`** to the grouped data. Here’s how to do that:

```python
# Aggregating data
aggregated = df.groupby('Region').agg({
    'Sales': ['sum', 'mean', 'count']
})
print(aggregated)
```

This summary shows total sales, average sales, and the number of entries for each region.

---

#### Step 3: Hands-on Exercise: Aggregating Sales Data by Region or Product

Now it's time to get hands-on! Use the following dataset to practise aggregating sales data:

```python
data = {
    'Product': ['A', 'B', 'C', 'A', 'B', 'C'],
    'Sales': [150, 200, 100, 180, 220, 140],
    'Quantity': [10, 20, 15, 25, 30, 20]
}

df = pd.DataFrame(data)

# Exercise 1: Group by 'Product' and calculate the total 'Sales'
grouped_product_sales = df.groupby('Product')['Sales'].sum()
print(grouped_product_sales)

# Exercise 2: Group by 'Product' and calculate the average 'Quantity'
grouped_product_quantity = df.groupby('Product')['Quantity'].mean()
print(grouped_product_quantity)

# Feel free to explore more aggregations!
```

---

#### Summary

In this lesson, we’ve covered:
- How to use the **`groupby()`** function in pandas.
- Aggregating data using **`sum()`**, **`mean()`**, and **`count()`**.
- Hands-on exercises to practise aggregating sales data by region or product.

---
[>> Next Lesson](./chapter3-2.md)