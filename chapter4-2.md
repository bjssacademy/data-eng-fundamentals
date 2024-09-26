## Chapter 4: Data Engineering Pipelines with pandas

### Lesson 2: Data Engineering Workflow with pandas

**Goal of this lesson:**  
In this lesson, you’ll build a simple ETL (Extract, Transform, Load) pipeline using pandas. This workflow is essential for data engineering tasks where you need to extract data from various sources, transform it, and load it into a destination.

---

#### Step 1: Understanding the ETL Process

The ETL process consists of three main stages:

1. **Extract:** Retrieve data from various sources.
2. **Transform:** Clean, filter, and format the data to make it suitable for analysis.
3. **Load:** Save the transformed data into a destination, such as a database or a CSV file.

---

#### Step 2: Building a Simple ETL Pipeline

Let’s create a simple ETL pipeline using pandas. We’ll extract data from a CSV file, transform it by cleaning and filtering the data, and then load it into another CSV file.

**Extracting Data**

```python
import pandas as pd

# Extract data from CSV
data = pd.read_csv('raw_sales_data.csv')
print(data.head())
```

**Transforming Data**

In this step, we might want to clean the data by removing duplicates and filtering out rows with missing values.

```python
# Removing duplicates
data = data.drop_duplicates()

# Filtering out rows where sales are less than zero
data = data[data['Sales'] >= 0]
```

You can also add new calculated columns or modify existing ones as part of the transformation process.

```python
# Adding a new column for total sales after tax
data['Total_Sales'] = data['Sales'] * 1.2  # Assuming a 20% tax
```

**Loading Data**

Finally, we’ll save the transformed data to a new CSV file.

```python
# Loading the cleaned data to a new CSV file
data.to_csv('cleaned_sales_data.csv', index=False)
print('Data loaded to cleaned_sales_data.csv')
```

---

#### Step 3: Hands-on Exercise: Create a Mini-ETL Pipeline Using Real-World Data

Now it’s your turn to practise building an ETL pipeline! Follow these steps:

1. **Extract data from a CSV file** named **`raw_customer_data.csv`** and display the first few rows.
  
   ```python
   customer_data = pd.read_csv('raw_customer_data.csv')
   print(customer_data.head())
   ```

2. **Transform the data** by:
   - Dropping duplicates.
   - Filtering out rows with missing values in critical columns.
   - Adding a new column for customer age based on the birth date.

   ```python
   customer_data = customer_data.drop_duplicates()
   customer_data = customer_data.dropna(subset=['Birth_Date'])  # Assuming Birth_Date is a critical column
   customer_data['Age'] = pd.to_datetime('today').year - pd.to_datetime(customer_data['Birth_Date']).dt.year
   ```

3. **Load the transformed data** into a new CSV file named **`cleaned_customer_data.csv`**.

   ```python
   customer_data.to_csv('cleaned_customer_data.csv', index=False)
   print('Cleaned customer data saved to cleaned_customer_data.csv')
   ```

---

#### Summary

In this lesson, we've covered:
- The steps involved in the ETL process: Extract, Transform, Load.
- How to build a simple ETL pipeline using pandas.
- A hands-on exercise to practise creating a mini-ETL pipeline using real-world data.


---
[>> Next Lesson](./chapter4-3.md)