## Chapter 4: Data Engineering Pipelines with pandas

### Lesson 1: Loading and Saving Data in Various Formats

**Goal of this lesson:**  
In this lesson, you'll learn how to read from and write to various data formats using pandas. This is fundamental for data engineering tasks, where data often comes from multiple sources.

---

#### Step 1: Reading Data from Different Formats

pandas supports a variety of file formats. Here’s how you can read data from CSV, Excel, JSON, and SQL databases.

**Reading CSV Files**

```python
import pandas as pd

# Reading a CSV file
csv_data = pd.read_csv('data.csv')
print(csv_data.head())
```

**Reading Excel Files**

```python
# Reading an Excel file
excel_data = pd.read_excel('data.xlsx', sheet_name='Sheet1')
print(excel_data.head())
```

**Reading JSON Files**

```python
# Reading a JSON file
json_data = pd.read_json('data.json')
print(json_data.head())
```

**Reading from SQL Databases**

You'll need a connection to your database. Here’s an example using SQLite:

```python
import sqlite3

# Create a connection to the database
conn = sqlite3.connect('database.db')

# Reading data from a SQL table
sql_data = pd.read_sql('SELECT * FROM table_name', conn)
print(sql_data.head())

# Don't forget to close the connection
conn.close()
```

---

#### Step 2: Saving Data to Various Formats

Just as you can read data, you can also save it back into various formats. Here’s how:

**Saving to CSV Files**

```python
# Saving DataFrame to a CSV file
csv_data.to_csv('output_data.csv', index=False)
```

**Saving to Excel Files**

```python
# Saving DataFrame to an Excel file
excel_data.to_excel('output_data.xlsx', index=False, sheet_name='Results')
```

**Saving to JSON Files**

```python
# Saving DataFrame to a JSON file
json_data.to_json('output_data.json', orient='records')
```

**Saving to SQL Databases**

Again, using SQLite as an example:

```python
# Create a connection to the database
conn = sqlite3.connect('database.db')

# Saving DataFrame to a SQL table
sql_data.to_sql('new_table_name', conn, if_exists='replace', index=False)

# Don't forget to close the connection
conn.close()
```

---

#### Step 3: Hands-on Exercise: Importing Data from Different Sources and Exporting the Results

Now it’s your turn! Use the following exercises to practice loading data from various formats and exporting results:

1. **Load a CSV file** named **`sales_data.csv`** and display the first five rows.
  
   ```python
   sales_data = pd.read_csv('sales_data.csv')
   print(sales_data.head())
   ```

2. **Load an Excel file** named **`customer_data.xlsx`** and display the first five rows of a specified sheet.
  
   ```python
   customer_data = pd.read_excel('customer_data.xlsx', sheet_name='Sheet1')
   print(customer_data.head())
   ```

3. **Load a JSON file** named **`products.json`** and display the first five rows.
  
   ```python
   products_data = pd.read_json('products.json')
   print(products_data.head())
   ```

4. **Combine all loaded data** into a single DataFrame, if applicable, and save it as a CSV file named **`combined_data.csv`**.

   ```python
   combined_data = pd.concat([sales_data, customer_data, products_data], ignore_index=True)
   combined_data.to_csv('combined_data.csv', index=False)
   ```

---

#### Summary

In this lesson, we've covered:
- How to read data from various formats including CSV, Excel, JSON, and SQL databases.
- How to save DataFrames back into different formats.
- A hands-on exercise to practise importing data from different sources and exporting the results.

---
[>> Next Lesson](./chapter4-2.md)