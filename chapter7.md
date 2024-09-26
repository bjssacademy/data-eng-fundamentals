### **Chapter 7: Final Project and Assessment**

#### **Lesson 1: Capstone Project Setup**

**Goal of this lesson**  
In this lesson, we’ll define your capstone project, which is the culmination of everything you’ve learned about pandas and NumPy in the context of data engineering. The aim is to design and implement a data engineering pipeline that extracts, cleans, transforms, and loads a dataset into a database.

**Defining the Project**  
For your final project, you'll choose a real-world dataset to work with. This could be anything from weather data, sales data, to financial data. The project should include the following steps:

1. **Extract**: Load the dataset from a file or an API.
2. **Clean**: Handle missing values, duplicates, and inconsistencies in the data.
3. **Transform**: Apply necessary transformations to prepare the data for analysis.
4. **Aggregate**: Summarise or group the data as needed.
5. **Load**: Store the cleaned and transformed data into a database (e.g., SQLite, PostgreSQL).

**Choosing Your Dataset**  
Here are a few suggestions for datasets you might consider:

- **Weather Data**: Use public datasets from sources like NOAA or open-meteo.
- **Sales Data**: Look for datasets on Kaggle related to retail sales.
- **Financial Data**: Consider using stock price data available through Yahoo Finance or Alpha Vantage.

**Hands-on Exercise**  
1. Choose a dataset and outline your project plan, including the steps you will take in your data engineering pipeline.
2. Document the sources of your dataset and the tools you will use (e.g., pandas, SQLAlchemy, etc.).

---

#### **Lesson 2: Capstone Project Implementation**

**Goal of this lesson**  
This lesson will guide you through the implementation of your capstone project. You’ll work through the various steps of the pipeline, applying what you’ve learned about pandas and NumPy.

**Step 1: Data Loading**  
Start by loading your dataset into a pandas DataFrame. Depending on the format of your dataset, you might use different methods:

```python
import pandas as pd

# Load data from a CSV file
data = pd.read_csv('your_dataset.csv')
```

**Step 2: Data Cleaning**  
Next, clean your data. This may involve:

- Removing duplicates
- Handling missing values
- Renaming columns for consistency

```python
# Remove duplicates
data.drop_duplicates(inplace=True)

# Fill missing values
data.fillna(method='ffill', inplace=True)

# Rename columns
data.rename(columns={'OldName': 'NewName'}, inplace=True)
```

**Step 3: Data Transformation**  
Transform your data to make it suitable for analysis. This could involve changing data types, creating new calculated columns, or filtering data.

```python
# Convert date column to datetime
data['date'] = pd.to_datetime(data['date'])

# Create a new column for profit
data['profit'] = data['sales'] - data['cost']
```

**Step 4: Data Aggregation**  
Aggregate your data as needed, using groupby operations.

```python
# Aggregate sales by month
monthly_sales = data.groupby(data['date'].dt.to_period('M')).sum()
```

**Step 5: Data Loading**  
Finally, load your cleaned and transformed data into a database. Use SQLAlchemy to connect to your database.

```python
from sqlalchemy import create_engine

# Create a connection to the database
engine = create_engine('sqlite:///your_database.db')

# Load data into a new SQL table
monthly_sales.to_sql('monthly_sales', con=engine, if_exists='replace', index=False)
```

**Hands-on Exercise**  
1. Implement the above steps in your Jupyter notebook or preferred IDE.
2. Make sure to comment your code and document any challenges you face along the way.

---

#### **Lesson 3: Capstone Project Review**

**Goal of this lesson**  
In this lesson, you will present your capstone project solution. You will walk through each component of your project, discussing the challenges you faced and the solutions you implemented.

**Presentation Structure**  
1. **Introduction**: Briefly describe your dataset and the purpose of your project.
2. **Pipeline Overview**: Provide an overview of your data engineering pipeline, outlining each step.
3. **Demonstration**: Show the code and results of each component of your project, explaining your thought process and decisions.
4. **Challenges and Solutions**: Discuss any obstacles you encountered during the project and how you resolved them.

**Hands-on Exercise**  
1. Prepare a presentation of your project using slides or a Jupyter notebook.
2. Include visualisations where applicable, such as charts or graphs to highlight key findings from your data.
3. Be ready to answer questions and provide explanations for your methodology.

---

### Congratulations!

Congratulations on completing the course! You’ve embarked on a longer journey through the world of data engineering by mastering essential skills in pandas and NumPy along the way. You've learned how to manipulate and analyse data effectively, perform data cleaning and transformation, and implement efficient data pipelines. With hands-on experience in loading, saving, and aggregating data, you've also gained valuable insights into working with real-world datasets. 

Your capstone project has not only demonstrated your newfound expertise but also prepared you to tackle challenges in the data engineering field with confidence. Well done!