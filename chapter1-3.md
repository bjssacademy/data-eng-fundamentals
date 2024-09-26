## Chapter 1: Introduction to Jupyter, NumPy, and pandas

### Lesson 3: Introduction to pandas

**Goal of this lesson:**  
By the end of this lesson, you’ll know what **pandas** is and why it’s vital for data manipulation. You’ll learn to create **DataFrames**, which are essentially tables, and start playing around with them.

---

#### What is pandas?

**pandas** is a Python library that makes data manipulation simple. While **NumPy** is great for handling numerical data, pandas is brilliant for structured data like **tables** or **spreadsheets**. It allows you to load, manipulate, and analyse data quickly, making it ideal for tasks like cleaning and transforming datasets.

Put simply, pandas gives you the tools to deal with all kinds of data in rows and columns, just like a spreadsheet, but with way more flexibility.

---

#### Step 1: Installing pandas

Let’s ensure you have pandas installed in your Jupyter Notebook environment. Open a new cell and run the following command:

```python
!pip install pandas
```

This command will install everything you need right within your notebook.

---

#### Step 2: Importing pandas and Creating a DataFrame

Once pandas is installed, let’s create a **DataFrame**. A DataFrame is essentially a table of data, similar to what you’d see in Excel or a database table.

1. First, import pandas:

```python
import pandas as pd
```

We use `pd` to keep things short and sweet.

2. Now, let’s create a simple DataFrame using some data:

```python
# Creating a DataFrame from a dictionary
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David'],
    'Age': [25, 32, 37, 29],
    'City': ['London', 'Manchester', 'Bristol', 'Liverpool']
}

df = pd.DataFrame(data)

print(df)
```

Output:

```
      Name  Age        City
0    Alice   25      London
1      Bob   32  Manchester
2  Charlie   37     Bristol
3    David   29   Liverpool
```

This is your first **DataFrame**! It’s a neat way to display data in rows and columns.

---

#### Step 3: Basic DataFrame Operations

Now that we’ve got some data, let’s start interacting with it.

1. **Viewing the first few rows**:

```python
print(df.head())  # Shows the first 5 rows by default
```

2. **Getting a specific column**:

```python
print(df['Name'])
```

This will give you just the `Name` column:

```
0      Alice
1        Bob
2    Charlie
3      David
Name: Name, dtype: object
```

3. **Getting a specific row by index**:

```python
print(df.iloc[2])  # Row with index 2 (third row)
```

You’ll see something like:

```
Name     Charlie
Age           37
City      Bristol
Name: 2, dtype: object
```

4. **Filtering data**: Let’s say we want to filter out people older than 30:

```python
adults = df[df['Age'] > 30]
print(adults)
```

The output will be:

```
      Name  Age        City
1      Bob   32  Manchester
2  Charlie   37     Bristol
```

You’ve just filtered your DataFrame to show only rows where `Age` is greater than 30.

---

#### Step 4: Adding, Removing, and Renaming Columns

1. **Adding a new column**: Let’s add a new column to the DataFrame.

```python
df['Salary'] = [45000, 54000, 58000, 47000]
print(df)
```

Now your table will have a new column:

```
      Name  Age        City  Salary
0    Alice   25      London   45000
1      Bob   32  Manchester   54000
2  Charlie   37     Bristol   58000
3    David   29   Liverpool   47000
```

2. **Removing a column**:

```python
df = df.drop('Salary', axis=1)  # Remove the 'Salary' column
print(df)
```

The `Salary` column is gone.

3. **Renaming columns**:

```python
df = df.rename(columns={'Name': 'Full Name'})
print(df)
```

Now the `Name` column has been renamed to `Full Name`.

---

#### Step 5: Loading Data from a CSV

In the real world, you’ll often load data from files, especially **CSV** (Comma Separated Values) files. Let’s load a CSV and explore it. First, make sure you’ve got a CSV file handy. If you don’t have one, you can download one or create a simple CSV file with Excel.

Here’s how you’d load a CSV file:

```python
df = pd.read_csv('your_file.csv')
print(df.head())
```

This will read the first few rows of your CSV file and print them out.

---

#### Summary

In this lesson, you’ve:
- Installed and imported **pandas** in your Jupyter Notebook.
- Created your first **DataFrame**.
- Performed basic operations like selecting rows and columns, filtering, and adding/removing columns.
- Learned how to load data from a CSV file.

**pandas** is an essential tool for working with structured data, and we’ll use it extensively throughout this course. Whether you're dealing with millions of rows of data or just a small dataset, pandas makes it quick and easy.

---

For more details about pandas, check out the official documentation [here](https://pandas.pydata.org/pandas-docs/stable/).

Next time, we’ll dive deeper into manipulating DataFrames and start getting into real data engineering tasks.

---
[>> Next Lesson](./chapter2-1.md)