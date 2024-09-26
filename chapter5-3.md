## Chapter 5: Advanced Techniques in NumPy and pandas for Data Engineering

### Lesson 3: Window Functions for Time Series and Rolling Data

**Goal of this lesson:**  
In this lesson, you'll learn about window functions in pandas, which are useful for calculating statistics over a rolling window of data, particularly in time series analysis.

---

#### Step 1: Introduction to Rolling Windows and Expanding Windows

Rolling windows allow you to perform calculations on a set of values within a specified window size that moves over your dataset. Expanding windows, on the other hand, calculate statistics over all preceding data points.

**Example of a Rolling Window:**

```python
import pandas as pd

# Create a sample time series DataFrame
dates = pd.date_range('2023-01-01', periods=10)
data = pd.Series(range(10), index=dates)

# Calculate a rolling mean with a window size of 3
rolling_mean = data.rolling(window=3).mean()
print(rolling_mean)
```

**Example of an Expanding Window:**

```python
# Calculate an expanding sum
expanding_sum = data.expanding().sum()
print(expanding_sum)
```

---

#### Step 2: Using Window Functions to Calculate Moving Averages and Other Time-based Operations

Window functions can be used to calculate moving averages, rolling sums, and other statistics that provide insights into trends over time.

**Example of Moving Averages:**

```python
# Calculate a moving average with a window size of 3
moving_avg = data.rolling(window=3).mean()
print(moving_avg)
```

**Example of Rolling Sum:**

```python
# Calculate a rolling sum with a window size of 2
rolling_sum = data.rolling(window=2).sum()
print(rolling_sum)
```

---

#### Step 3: Hands-on Exercise: Implement Rolling Statistics on Time-Series Data

Now it’s your turn to apply window functions! Follow these exercises:

1. **Create a time series DataFrame** with random data.

   ```python
   import numpy as np
   
   # Create a time series DataFrame with random data
   np.random.seed(0)
   dates = pd.date_range('2023-01-01', periods=20)
   data = pd.Series(np.random.randn(20), index=dates)
   ```

2. **Calculate the rolling mean** with a window size of 5 and display the results.

   ```python
   rolling_mean = data.rolling(window=5).mean()
   print(rolling_mean)
   ```

3. **Calculate the rolling standard deviation** with a window size of 4.

   ```python
   rolling_std = data.rolling(window=4).std()
   print(rolling_std)
   ```

4. **Use the expanding method** to calculate the cumulative sum and display it.

   ```python
   expanding_sum = data.expanding().sum()
   print(expanding_sum)
   ```

---

#### Summary

In this lesson, we've covered:
- The concept of rolling and expanding windows in pandas.
- How to calculate rolling averages, sums, and other statistics.
- A hands-on exercise to implement rolling statistics on time-series data.


---
[>> Next Lesson](./chapter6.md)