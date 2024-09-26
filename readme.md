# Data Engineering - Fundamentals

Welcome! This course assumes you have some decent programming knowledge. We're going to be using Python, but any knowledge should be fine.

## Setup: Installing Python and pip

Before we can start using all the cool tools like **Jupyter**, **NumPy**, and **pandas**, we need to make sure **Python** and **pip** are installed. These two are the foundation for everything else. Don't worry, it’s pretty straightforward, and I’ll guide you through the steps.

---

### Step 1: Installing Python

First things first, we need to install **Python**. Python is the programming language we’ll be using throughout the course.

#### Windows

1. Head over to the official Python website [here](https://www.python.org/downloads/).
2. Download the latest version of Python for Windows (it’ll detect your operating system automatically).
3. **Important**: During the installation, make sure to check the box that says **Add Python to PATH**. This will save you a lot of headaches later on.
4. Follow the installation instructions, clicking through the prompts until it’s done.

#### macOS

If you’re on a Mac, you’ve got Python pre-installed, but it’s often an older version, so let’s update it.

1. Again, head to the [Python website](https://www.python.org/downloads/) and download the latest version for macOS.
2. Run the installer and follow the instructions.
3. That’s it – simple!

#### Linux

Most Linux distributions come with Python pre-installed, but to check, open your terminal and type:

```bash
python3 --version
```

If it shows a version number (e.g., `Python 3.8.5`), you’re good to go. If not, install it with:

```bash
sudo apt-get update
sudo apt-get install python3
```

---

### Step 2: Installing pip

**pip** is Python’s package manager, and it lets us install libraries like **NumPy** and **pandas**. It usually comes with Python, but we’ll double-check just to be sure.

#### Check if pip is already installed

Open your terminal (or command prompt on Windows) and type:

```bash
pip --version
```

If you see something like this, you’re all set:

```
pip 21.0.1 from /usr/local/lib/python3.9/site-packages (python 3.9)
```

#### Installing pip (if it’s missing)

If pip isn’t installed, here’s how to get it sorted.

1. **Windows/macOS**: It should come with Python. If you’re missing it, try reinstalling Python (make sure you check the **Add Python to PATH** box).
2. **Linux**: Run the following command in your terminal:

```bash
sudo apt-get install python3-pip
```

---

### Step 3: Verifying the Installation

Let’s make sure everything is working properly.

1. Open your terminal or command prompt.
2. Type the following to check your Python installation:

```bash
python --version
```

You should see something like this:

```
Python 3.9.1
```

If you see something similar, that means Python is installed correctly.

3. Now check if pip is working:

```bash
pip --version
```

You should get something like:

```
pip 21.0.1
```

---

### That’s it!

You’re all set now. Python and pip are installed, and you're ready to dive into the lessons. If you run into any issues, check out the official Python documentation for troubleshooting tips [here](https://docs.python.org/3/).

Now, whenever we mention running commands like `pip install pandas`, you’ll know exactly what to do.

---

## Contents

### **Chapter 1: Introduction to Jupyter, NumPy, and pandas**

#### **[Lesson 1: Getting Started with Jupyter Notebook](./chapter1-1.md)**
- Overview of Jupyter Notebook
- Navigating the interface: Code cells, Markdown, and output
- Writing basic Python code in Jupyter

#### **[Lesson 2: Introduction to NumPy](./chapter1-2.md)**
- What is NumPy and why is it important?
- Creating arrays: `numpy.array()`
- Basic operations on NumPy arrays (element-wise operations, reshaping)
- Hands-on exercise: Basic array manipulations

#### **[Lesson 3: Introduction to pandas](./chapter1-3.md)**
- What is pandas and why is it used?
- Understanding Series and DataFrames
- Creating a pandas DataFrame from scratch
- Hands-on exercise: Creating a simple DataFrame and performing basic operations

---

### **Chapter 2: Data Manipulation with pandas and NumPy**

#### **[Lesson 1: Indexing and Slicing DataFrames](./chapter2-1.md)**
- Accessing rows and columns using `.loc[]` and `.iloc[]`
- Boolean indexing and filtering
- Hands-on exercise: Filtering data from a DataFrame

#### **[Lesson 2: NumPy Arrays for Performance Optimization](./chapter2-2.md)**
- Why use NumPy arrays in data engineering tasks
- Using `numpy.where()` for conditional operations
- Hands-on exercise: Using NumPy to optimize operations in a pandas DataFrame

#### **[Lesson 3: Data Cleaning and Transformation with pandas](./chapter2-3.md)**
- Handling missing data (`dropna()`, `fillna()`)
- Renaming columns, dropping columns, and replacing values
- Hands-on exercise: Cleaning a raw dataset

#### **[Lesson 4: Working with Dates and Times](./chapter2-4.md)**
- Using `pd.to_datetime()` for date conversion
- Extracting date components (year, month, etc.)
- Hands-on exercise: Parsing and analyzing time-series data

---

### **Chapter 3: Aggregating, Grouping, and Merging Data**

#### **Lesson 1: Aggregation and GroupBy**
- Understanding the `groupby()` function
- Aggregating data using `sum()`, `mean()`, `count()`
- Hands-on exercise: Aggregating sales data by region or product

#### **Lesson 2: Merging and Joining DataFrames**
- Combining data with `merge()`, `concat()`, and `join()`
- Understanding different types of joins (inner, outer, left, right)
- Hands-on exercise: Joining two datasets (e.g., customer data and order data)

#### **Lesson 3: Working with Large Datasets**
- Chunking data using `chunksize` in pandas
- Memory-efficient operations in pandas
- Hands-on exercise: Reading and processing large CSV files

---

### **Chapter 4: Data Engineering Pipelines with pandas**

#### **Lesson 1: Loading and Saving Data in Various Formats**
- Reading and writing data from/to CSV, Excel, JSON, SQL databases
- Hands-on exercise: Importing data from different sources and exporting the results

#### **Lesson 2: Data Engineering Workflow with pandas**
- Building a simple ETL pipeline with pandas
- Data extraction, transformation, and loading processes
- Hands-on exercise: Create a mini-ETL pipeline using real-world data

#### **Lesson 3: Handling Data Quality Issues**
- Identifying and handling duplicates
- Data validation and constraints
- Hands-on exercise: Detect and fix quality issues in a dataset

---

### **Chapter 5: Advanced Techniques in NumPy and pandas for Data Engineering**

#### **Lesson 1: Vectorization and Broadcasting in NumPy**
- What is vectorization and why is it important?
- Using NumPy’s broadcasting for efficient data manipulation
- Hands-on exercise: Implement vectorized operations on large datasets

#### **Lesson 2: Applying Functions with pandas (`apply()` and `map()`)**
- Using `apply()`, `map()`, and `applymap()` for transformation
- Lambda functions and custom transformations
- Hands-on exercise: Apply custom functions across DataFrame columns

#### **Lesson 3: Window Functions for Time Series and Rolling Data**
- Introduction to rolling windows and expanding windows
- Using window functions to calculate moving averages and other time-based operations
- Hands-on exercise: Implement rolling statistics on time-series data

---

### **Chapter 6: pandas and NumPy in Real-world Data Engineering**

#### **Lesson 1: Data Engineering in Big Data Environments**
- Optimizing pandas for large-scale data
- Introduction to Dask and PySpark as pandas alternatives for distributed environments
- Hands-on exercise: Explore Dask or PySpark for large-scale DataFrame operations

#### **Lesson 2: Integrating pandas with Databases**
- Connecting pandas with SQL databases using `SQLAlchemy`
- Loading data from and into SQL databases
- Hands-on exercise: Extract data from a database, transform it, and load it back

---

### **Chapter 7: Final Project and Assessment**

#### **Lesson 1: Capstone Project Setup**
- Define the final project: Design and implement a data engineering pipeline that extracts, cleans, transforms, and loads a dataset into a database
- Use real-world data (e.g., weather data, sales data, or financial data)

#### **Lesson 2: Capstone Project Implementation**
- Guided implementation of the project
- Cover all steps: data loading, cleaning, transformation, aggregation, and final storage

#### **Lesson 3: Capstone Project Review**
- Present the project solution, walk through each component, and discuss challenges and solutions

