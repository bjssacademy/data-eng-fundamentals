## Chapter 3: Aggregating, Grouping, and Merging Data

### Lesson 3: Working with Large Datasets

**Goal of this lesson:**  
In this lesson, you’ll learn how to efficiently handle large datasets in pandas, which is crucial for data engineering tasks. We’ll explore techniques for chunking data and performing memory-efficient operations.

---

#### Step 1: Chunking Data Using `chunksize`

When dealing with large datasets, it’s often impractical to load the entire dataset into memory at once. The **`chunksize`** parameter allows you to read large files in smaller, more manageable chunks. Here’s how you can do that:

```python
import pandas as pd

# Reading a large CSV file in chunks
chunk_size = 1000  # Number of rows per chunk
chunks = pd.read_csv('large_dataset.csv', chunksize=chunk_size)

# Processing each chunk
for chunk in chunks:
    # Perform operations on each chunk
    print(chunk.head())  # Just an example operation
```

In this example, we read a CSV file in chunks of 1000 rows, allowing us to process the data without exhausting memory.

---

#### Step 2: Memory-efficient Operations in pandas

To work efficiently with large datasets, consider these practices:

- **Use `category` data type:** This can significantly reduce memory usage for categorical variables.
  
  ```python
  df['CategoryColumn'] = df['CategoryColumn'].astype('category')
  ```

- **Select only necessary columns:** When loading data, specify only the columns you need.
  
  ```python
  df = pd.read_csv('large_dataset.csv', usecols=['Column1', 'Column2'])
  ```

- **Drop unnecessary rows:** Filter out rows you don’t need as soon as possible.

  ```python
  df = df[df['Column1'] > 0]  # Example filter
  ```

---

#### Step 3: Hands-on Exercise: Reading and Processing Large CSV Files

Now it’s time to put your skills to the test! Use this exercise to read and process a large CSV file. You can create a mock CSV file or use an actual large dataset.

```python
# Example of processing a large CSV in chunks
chunk_size = 1000
chunks = pd.read_csv('your_large_file.csv', chunksize=chunk_size)

# Exercise: Calculate the total sales from a large dataset
total_sales = 0

for chunk in chunks:
    total_sales += chunk['Sales'].sum()  # Assuming there’s a 'Sales' column

print(f'Total Sales: {total_sales}')
```

In this exercise, you’ll read the dataset in chunks and calculate the total sales by summing the **Sales** column from each chunk.

---

#### Summary

In this lesson, we’ve covered:
- How to read large datasets in chunks using the **`chunksize`** parameter.
- Techniques for memory-efficient operations in pandas, like using the `category` type and selecting necessary columns.
- A hands-on exercise to practise reading and processing large CSV files.

---
[>> Next Lesson](./chapter4-1.md)