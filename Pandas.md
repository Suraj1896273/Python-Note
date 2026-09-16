# Pandas — Basic Understanding

## What is Pandas?

**Pandas** is a Python library used for **data manipulation, data analysis, and data cleaning**.

It helps us work with data in the form of **tables**, similar to Excel spreadsheets.

### Simple Definition

> **Pandas is a Python library used to store, clean, analyze, and manipulate structured data.**

---

# Why Do We Use Pandas?

Pandas is mainly used to:

- Read data from files
- Create and store data
- Clean missing or incorrect data
- Select and filter data
- Sort data
- Analyze data
- Group data
- Perform calculations
- Work with large datasets

---

# Installing Pandas

If Pandas is not installed, use:


pip install pandas

# Pandas Series

## What is Pandas Series?

**Pandas Series** is a one-dimensional data structure in Pandas.

It stores data in the form of values along with an index.

### Simple Definition

> A Pandas Series is a one-dimensional labeled data structure used to store a collection of values.

---

## Creating a Series

We can create a Series using `pd.Series()`.

```python
import pandas as pd

s = pd.Series(["Ind", "Aus", "NZ"])

print(s)
```

# Pandas DataFrame

## What is a Pandas DataFrame?

A **Pandas DataFrame** is a two-dimensional data structure in Pandas.

It stores data in the form of **rows and columns**, similar to an Excel spreadsheet or a database table.

### Simple Definition

> A Pandas DataFrame is a two-dimensional labeled data structure used to store, manipulate, and analyze structured data.

---

# Why Do We Use DataFrame?

DataFrame is mainly used to:

- Store data in rows and columns
- Read data from CSV and Excel files
- Clean data
- Filter data
- Sort data
- Analyze data
- Handle missing values
- Group data
- Perform calculations
- Prepare data for Data Science and Machine Learning

---

# Creating a DataFrame

We can create a DataFrame using `pd.DataFrame()`.

```python
import pandas as pd

data = {
    "name": ["Rahul", "Priya", "Amit", "Sneha"],
    "employee_id": [101, 102, 103, 104],
    "age": [25, 23, 28, 26],
    "city": ["Kolkata", "Siliguri", "Delhi", "Mumbai"]
}

df = pd.DataFrame(data)

print(df)
```

# Output :-
# Pandas DataFrame

## What is a Pandas DataFrame?

A **Pandas DataFrame** is a two-dimensional data structure in Pandas.

It stores data in the form of **rows and columns**, similar to an Excel spreadsheet or a database table.

### Simple Definition

> A Pandas DataFrame is a two-dimensional labeled data structure used to store, manipulate, and analyze structured data.

---

# Why Do We Use DataFrame?

DataFrame is mainly used to:

- Store data in rows and columns
- Read data from CSV and Excel files
- Clean data
- Filter data
- Sort data
- Analyze data
- Handle missing values
- Group data
- Perform calculations
- Prepare data for Data Science and Machine Learning

---

# Creating a DataFrame

We can create a DataFrame using `pd.DataFrame()`.

```python
import pandas as pd

data = {
    "name": ["Rahul", "Priya", "Amit", "Sneha"],
    "employee_id": [101, 102, 103, 104],
    "age": [25, 23, 28, 26],
    "city": ["Kolkata", "Siliguri", "Delhi", "Mumbai"]
}

df = pd.DataFrame(data)

print(df)
```
