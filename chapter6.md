## Chapter 6: pandas and NumPy in Real-world Data Engineering

> :exclamation: From here we'll be moving out of Jupyter and using your preferred IDE. We used VS Code, but people also use PyCharm.

### Lesson 1: Data Engineering in Big Data Environments

**Goal of this lesson:**  
In this lesson, you'll learn how to optimise pandas for large-scale data and explore alternatives like Dask and PySpark that are designed for distributed environments.

---

#### Step 1: Optimizing pandas for Large-scale Data

When working with large datasets in pandas, you may run into performance issues. Here are a few strategies to optimise pandas:

- **Use Efficient Data Types**: Convert your data to more memory-efficient types. For example, use `category` for categorical variables.
  
  ```python
  df['category_column'] = df['category_column'].astype('category')
  ```

- **Chunking**: Read large files in chunks instead of loading the entire file into memory.

  ```python
  for chunk in pd.read_csv('large_file.csv', chunksize=1000):
      # Process each chunk
      print(chunk.head())
  ```

- **Memory Management**: Use `DataFrame.memory_usage()` to check memory consumption and drop unused columns.

  ```python
  df.drop(columns=['unused_column'], inplace=True)
  ```

---

#### Step 2: Introduction to Dask and PySpark as pandas Alternatives for Distributed Environments

For very large datasets, you may want to consider using Dask or PySpark, which are designed for distributed data processing.

**Dask** allows you to work with large datasets that don't fit in memory by breaking them into smaller pieces.

```python
import dask.dataframe as dd

# Reading a large CSV file with Dask
dask_df = dd.read_csv('large_file.csv')
print(dask_df.head())
```

**PySpark** is another powerful tool for big data processing, using the Spark framework to distribute computations across a cluster.

```python
from pyspark.sql import SparkSession

# Create a Spark session
spark = SparkSession.builder.appName('example').getOrCreate()

# Reading a large CSV file with PySpark
spark_df = spark.read.csv('large_file.csv', header=True, inferSchema=True)
spark_df.show()
```

---

#### Step 3: Hands-on Exercise: Explore Dask or PySpark for Large-scale DataFrame Operations

Choose either Dask or PySpark for this exercise.

1. **Set up Dask**: If you choose Dask, install it using pip:

   ```bash
   pip install dask[complete]
   ```

   Then, perform operations on a large dataset:

   ```python
   import dask.dataframe as dd

   # Read a large CSV file
   dask_df = dd.read_csv('large_file.csv')

   # Calculate the mean of a column
   mean_value = dask_df['column_name'].mean().compute()
   print(mean_value)
   ```

2. **Set up PySpark**: If you choose PySpark, install it using pip:

   ```bash
   pip install pyspark
   ```

   Then, perform operations on a large dataset:

   ```python
   from pyspark.sql import SparkSession

   spark = SparkSession.builder.appName('example').getOrCreate()

   # Read a large CSV file
   spark_df = spark.read.csv('large_file.csv', header=True, inferSchema=True)

   # Calculate the mean of a column
   mean_value = spark_df.agg({'column_name': 'mean'}).collect()
   print(mean_value)
   ```

---

### Lesson 2: Integrating pandas with Databases

**Goal of this lesson:**  
In this lesson, you'll learn how to connect pandas with SQL databases using SQLAlchemy, and how to load and extract data from these databases.

---

#### Step 1: Connecting pandas with SQL Databases using SQLAlchemy

To connect pandas with SQL databases, you'll need SQLAlchemy installed.

```bash
pip install sqlalchemy
```

Here's how to connect to a SQLite database:

```python
from sqlalchemy import create_engine

# Create a SQLAlchemy engine
engine = create_engine('sqlite:///database.db')
```

---

#### Step 2: Loading Data from and into SQL Databases

Once connected, you can easily load data from SQL tables into pandas DataFrames and write DataFrames back into SQL tables.

> :exclamation: don't forget you'll need to pip install pandas!

**Load Data from SQL Table:**

```python
# Load data from a SQL table
df = pd.read_sql('SELECT * FROM table_name', engine)
print(df.head())
```

**Write Data to SQL Table:**

```python
# Write DataFrame to a SQL table
df.to_sql('new_table_name', engine, if_exists='replace', index=False)
```

---

#### Step 3: Hands-on Exercise: Extract Data from a Database, Transform It, and Load It Back

1. **Extract Data**: Load data from a SQL database into a DataFrame.

   ```python
   df = pd.read_sql('SELECT * FROM sales', engine)
   print(df.head())
   ```

2. **Transform Data**: Perform some transformations, such as calculating total sales.

   ```python
   df['total_sales'] = df['price'] * df['quantity']
   ```

3. **Load Data**: Write the transformed DataFrame back to the database.

   ```python
   df.to_sql('sales_transformed', engine, if_exists='replace', index=False)
   ```

---
#### Summary

In this chapter, we've covered:
- How to optimise pandas for large-scale data engineering.
- Connecting pandas with SQL databases and performing data extraction and loading.

---
[>> Next Lesson](./chapter7.md)