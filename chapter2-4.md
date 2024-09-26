## Chapter 2: Data Manipulation with pandas and NumPy

### Lesson 4: Working with Dates and Times

**Goal of this lesson:**  
In this lesson, you’ll learn how to work with dates and times in pandas, which is critical in many data engineering tasks such as time-series analysis, monitoring, and scheduling.

---

#### Step 1: Using `pd.to_datetime()` for Date Conversion

Often, dates are stored as strings in raw data. **pandas** provides **`pd.to_datetime()`** to convert these strings into **datetime** objects.

Let’s start with a simple example:

```python
import pandas as pd

# Sample data with date strings
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David'],
    'Join_Date': ['2023-01-15', '2022-06-24', '2021-03-10', '2020-12-19']
}

df = pd.DataFrame(data)

# Convert the 'Join_Date' column to datetime
df['Join_Date'] = pd.to_datetime(df['Join_Date'])
print(df)
```

Now, the **`Join_Date`** column contains **datetime** objects, making it easier to work with dates in pandas.

---

#### Step 2: Extracting Date Components

Once you’ve converted your strings to **datetime** objects, you can easily extract specific components like the year, month, or day.

1. **Extracting the year:**

```python
df['Year'] = df['Join_Date'].dt.year
print(df)
```

2. **Extracting the month:**

```python
df['Month'] = df['Join_Date'].dt.month
print(df)
```

3. **Extracting the day of the week:**

```python
df['Day_of_Week'] = df['Join_Date'].dt.day_name()
print(df)
```

---

#### Step 3: Handling Time-Series Data

If you’re working with time-series data (such as monitoring logs or stock prices), you’ll often need to set a **datetime** column as the index for easier analysis. Let’s look at an example:

```python
# Sample time-series data
data = {
    'Date': ['2024-09-01', '2024-09-02', '2024-09-03', '2024-09-04'],
    'Value': [100, 110, 105, 115]
}

df_ts = pd.DataFrame(data)

# Convert 'Date' to datetime and set as index
df_ts['Date'] = pd.to_datetime(df_ts['Date'])
df_ts.set_index('Date', inplace=True)

print(df_ts)
```

With the **Date** column set as the index, you can now perform time-based operations more easily.

---

#### Step 4: Hands-on Exercise: Parsing and Analysing Time-Series Data

Now it’s your turn to play with some time-series data. Try the following tasks with this dataset:

```python
data = {
    'Date': ['2024-01-01', '2024-02-01', '2024-03-01', '2024-04-01'],
    'Temperature': [5.2, 7.4, 10.1, 12.8]
}

df_weather = pd.DataFrame(data)

# Exercise 1: Convert the 'Date' column to datetime
df_weather['Date'] = pd.to_datetime(df_weather['Date'])
print(df_weather)

# Exercise 2: Extract the month and year from the 'Date' column
df_weather['Month'] = df_weather['Date'].dt.month
df_weather['Year'] = df_weather['Date'].dt.year
print(df_weather)

# Exercise 3: Set the 'Date' column as the index and view the DataFrame
df_weather.set_index('Date', inplace=True)
print(df_weather)
```

---

#### Summary

In this lesson, we’ve covered:
- How to use **`pd.to_datetime()`** to convert date strings to datetime objects.
- Extracting date components like year, month, and day of the week.
- Handling time-series data and setting a **datetime** column as the index.
- Hands-on exercises to practice working with dates and times.

---
[>> Next Lesson](./chapter3-1.md)