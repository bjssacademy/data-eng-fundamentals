## Chapter 2: Data Manipulation with pandas and NumPy

### Lesson 1: Indexing and Slicing DataFrames

**Goal of this lesson:**  
By the end of this lesson, you’ll know how to access specific rows and columns in a DataFrame, filter data, and work with Boolean indexing.

---

#### Step 1: Accessing Rows and Columns

There are two main ways to access parts of your **pandas** DataFrame: **`.loc[]`** and **`.iloc[]`**. Let’s break them down.

- **`.loc[]`** is used to access data using **labels** (like row or column names).
- **`.iloc[]`** is used to access data using **integer positions** (like row and column numbers).

Let’s use a sample DataFrame:

```python
import pandas as pd

# Sample data
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David'],
    'Age': [25, 32, 37, 29],
    'City': ['London', 'Manchester', 'Bristol', 'Liverpool']
}

df = pd.DataFrame(data)
```

---

#### Accessing rows and columns with `.loc[]`

1. **Accessing a specific row by label:**

Let’s get the row where the person’s name is `Bob`:

```python
row = df.loc[1]  # Row with index 1
print(row)
```

Output:

```
Name       Bob
Age         32
City    Manchester
Name: 1, dtype: object
```

2. **Accessing specific columns by label:**

You can select multiple columns by their names:

```python
columns = df.loc[:, ['Name', 'City']]
print(columns)
```

Output:

```
      Name        City
0    Alice      London
1      Bob  Manchester
2  Charlie     Bristol
3    David   Liverpool
```

---

#### Accessing rows and columns with `.iloc[]`

1. **Accessing by row and column index:**

Let’s get the second row and second column using their positions:

```python
value = df.iloc[1, 1]  # Second row, second column (Age of Bob)
print(value)
```

Output:

```
32
```

2. **Accessing a range of rows and columns:**

You can slice the DataFrame by providing start and end positions:

```python
subset = df.iloc[0:2, 0:2]  # First two rows, first two columns
print(subset)
```

Output:

```
    Name  Age
0  Alice   25
1    Bob   32
```

---

#### Step 2: Boolean Indexing and Filtering

Boolean indexing is incredibly useful when you want to filter your data based on conditions. Let’s say we want to filter out people older than 30.

1. **Filtering based on a condition:**

```python
adults = df[df['Age'] > 30]
print(adults)
```

Output:

```
      Name  Age      City
1      Bob   32  Manchester
2  Charlie   37     Bristol
```

2. **Combining multiple conditions:**

What if we want people older than 30 who live in **Bristol**? We can combine conditions like this:

```python
filtered = df[(df['Age'] > 30) & (df['City'] == 'Bristol')]
print(filtered)
```

Output:

```
      Name  Age     City
2  Charlie   37  Bristol
```

The **`&`** symbol is used to combine multiple conditions (think of it like an “AND” in logic).

---

#### Step 3: Hands-on Exercise: Filtering Data from a DataFrame

Now, it’s your turn to try filtering! Use the following dataset and apply filters based on different conditions.

```python
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
    'Age': [25, 32, 37, 29, 45],
    'City': ['London', 'Manchester', 'Bristol', 'Liverpool', 'Leeds']
}

df = pd.DataFrame(data)

# Exercise 1: Filter for people younger than 35
print(df[df['Age'] < 35])

# Exercise 2: Filter for people older than 30 and living in London
print(df[(df['Age'] > 30) & (df['City'] == 'London')])

# Try adding more conditions and see what you can come up with!
```

---

#### Summary

In this lesson, we’ve covered:
- Accessing rows and columns with **`.loc[]`** and **`.iloc[]`**.
- Filtering data using **Boolean indexing**.
- Hands-on exercises to practice what you’ve learned.

---

Next time, we’ll dig into **NumPy** and how it can speed up performance in **pandas** for data engineering tasks. It’ll be a game changer once you start working with larger datasets.

---
[>> Next Lesson](./chapter2-2.md)
