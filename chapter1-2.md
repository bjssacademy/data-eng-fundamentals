## Chapter 1: Introduction to Jupyter, NumPy, and pandas

### Lesson 2: Introduction to NumPy

**Goal of this lesson:**  
By the end of this lesson, you’ll have a good grasp of what **NumPy** is and why it’s essential for data engineering. We’ll play around with **NumPy arrays** and explore some basic operations in a Jupyter notebook.

---

#### What is NumPy?

**NumPy** (Numerical Python) is a fundamental Python library used for numerical computing. It’s the backbone of most data processing in Python because it makes handling large datasets more efficient. While regular Python lists are good, they’re slow when you’re working with huge amounts of data. NumPy, on the other hand, uses arrays that are super fast and memory-efficient, perfect for data engineers.

---

#### Step 1: Installing NumPy

If you don’t have NumPy installed yet, you can install it directly from your Jupyter notebook using the following command:

```python
!pip install numpy
```

> :exclamation: This is slightly different to how you install packages in python normally, as in Jupyter you add the `!` character before the `pip` command.

This will install NumPy, allowing you to start using it immediately.

---

#### Step 2: Creating NumPy Arrays

Arrays in NumPy are like Python lists, but faster and more powerful. Let’s create a few and see how they work.

1. First, import NumPy:

```python
import numpy as np
```

(We typically shorten `numpy` to `np` for convenience.)

2. Now, create a simple array:

```python
# Creating a basic NumPy array
array_1 = np.array([1, 2, 3, 4, 5])

print(array_1)
```

When you run this (Shift+Enter), you should see:

```
[1 2 3 4 5]
```

**Note**: It looks similar to a Python list, but trust me, NumPy arrays are way more efficient.

---

#### Step 3: Array Shapes and Dimensions

Let’s check the **shape** of this array and see how NumPy handles dimensions.

```python
# Check the shape of the array
print(array_1.shape)
```

You’ll see something like:

```
(5,)
```

This means the array has 5 elements in a single dimension. We can create multi-dimensional arrays too, like matrices:

```python
# Creating a 2D array (matrix)
array_2d = np.array([[1, 2, 3], [4, 5, 6]])

print(array_2d)
print("Shape:", array_2d.shape)
```

Output:

```
[[1 2 3]
 [4 5 6]]
Shape: (2, 3)
```

This tells us that `array_2d` has 2 rows and 3 columns.

---

#### Step 4: Basic Operations on NumPy Arrays

One of the reasons NumPy is so popular is its speed in performing operations. Let’s try some basic element-wise operations:

```python
# Adding 2 to every element
print(array_1 + 2)

# Multiplying every element by 10
print(array_1 * 10)
```

You should see:

```
[3 4 5 6 7]
[10 20 30 40 50]
```

Notice how every element of the array was updated without using a loop. This kind of operation is called **vectorisation** – it’s fast and ideal when working with large datasets.

---

#### Step 5: Reshaping Arrays

As a data engineer, you’ll often need to change the shape of your data. For example, you might have a flat array (1D) that you need to reshape into a matrix (2D) or even a 3D array for some processing. Let’s see how that works:

```python
# Reshaping a flat array into a 2D array
array_reshaped = np.array([1, 2, 3, 4, 5, 6]).reshape(2, 3)

print(array_reshaped)
```

This will output:

```
[[1 2 3]
 [4 5 6]]
```

We’ve turned a 1D array with 6 elements into a 2D array with 2 rows and 3 columns. Handy, right?

---

#### Step 6: Quick Operations to Know

Here are a few basic operations that you’ll use a lot with NumPy:

1. **Sum** of all elements:

```python
print(np.sum(array_1))
```

2. **Mean** (average) of the elements:

```python
print(np.mean(array_1))
```

3. **Standard Deviation**:

```python
print(np.std(array_1))
```

---

#### Summary

In this lesson, you’ve:
- Installed and imported **NumPy**.
- Created your first **NumPy arrays**.
- Performed basic operations on arrays (addition, multiplication).
- Learned about **array shapes** and **reshaping**.
- Performed quick statistical operations like sum, mean, and standard deviation.

We’re just scratching the surface here, but you can already see why NumPy is a key tool for working with data. It’s fast and efficient, making it perfect for handling large datasets.

---

Feel free to explore more about NumPy on their official page [here](https://numpy.org/doc/stable/).

Next time, we’ll dive into **pandas**, where we’ll start working with DataFrames, the bread and butter of data manipulation.


---
[>> Next Lesson](./chapter1-3.md)