## Chapter 5: Advanced Techniques in NumPy and pandas for Data Engineering

### Lesson 1: Vectorization and Broadcasting in NumPy

**Goal of this lesson:**  
In this lesson, you'll learn about vectorization and broadcasting in NumPy. These techniques are crucial for optimising performance and efficiency when working with large datasets.

---

#### Step 1: What is Vectorization and Why is it Important?

Vectorization refers to the process of converting algorithms from operating on a single value at a time to operating on a set of values simultaneously. This is important because it significantly speeds up computations, as it leverages low-level optimisations in libraries like NumPy.

**Example of Vectorization:**

Instead of using a for loop to perform operations on array elements, you can use NumPy’s built-in functions, which are implemented in C and are much faster.

```python
import numpy as np

# Create a large array
data = np.random.rand(1000000)

# Without vectorization (using a loop)
squared = np.array([x**2 for x in data])

# With vectorization
squared_vectorized = data**2
```

---

#### Step 2: Using NumPy’s Broadcasting for Efficient Data Manipulation

Broadcasting allows NumPy to work with arrays of different shapes during arithmetic operations. This can simplify your code and improve performance.

**Example of Broadcasting:**

```python
# Create a 1D array and a 2D array
array_1d = np.array([1, 2, 3])
array_2d = np.array([[10, 20, 30], [40, 50, 60]])

# Broadcasting the 1D array across the 2D array
result = array_2d + array_1d
print(result)
```

In this example, the 1D array is "stretched" to match the shape of the 2D array, allowing for element-wise addition.

---

#### Step 3: Hands-on Exercise: Implement Vectorized Operations on Large Datasets

Now it’s your turn to practise vectorization and broadcasting! Follow these steps:

1. **Create a large NumPy array** of random numbers and perform some vectorized operations.
  
   ```python
   large_data = np.random.rand(1000000)

   # Calculate the square root of each element
   sqrt_data = np.sqrt(large_data)
   ```

2. **Create another array** and use broadcasting to perform operations on it.
  
   ```python
   # Create a 1D array
   add_array = np.array([5, 10, 15])

   # Create a 2D array
   large_2d_data = np.random.rand(3, 3)

   # Broadcast the 1D array to add to the 2D array
   broadcast_result = large_2d_data + add_array
   print(broadcast_result)
   ```

3. **Explore the performance difference** by timing the vectorized operations vs. a traditional loop.
  
   ```python
   import time

   # Timing the loop
   start_time = time.time()
   loop_result = np.array([x**2 for x in large_data])
   loop_time = time.time() - start_time

   # Timing the vectorized operation
   start_time = time.time()
   vectorized_result = large_data**2
   vectorized_time = time.time() - start_time

   print(f'Time taken (loop): {loop_time:.5f} seconds')
   print(f'Time taken (vectorized): {vectorized_time:.5f} seconds')
   ```

---

#### Summary

In this lesson, we've covered:
- The concept of vectorization and its importance in data processing.
- How to use broadcasting for efficient operations on arrays of different shapes.
- A hands-on exercise to practise implementing vectorized operations on large datasets.

---
[>> Next Lesson](./chapter5-2.md)