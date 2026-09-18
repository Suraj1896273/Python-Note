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
mport pandas as pd

data = {
    "name": ["Rahul", "Priya", "Amit", "Sneha"],
    "employee_id": [101, 102, 103, 104],
    "age": [25, 23, 28, 26],
    "city": ["Kolkata", "Siliguri", "Delhi", "Mumbai"]
}

print(data)

Emply_Details = pd.DataFrame(data)
print(Emply_Details)

```

## Basic Difference Between Series and DataFrame

- **Series** → Contains **one column** of data with an index.
- **DataFrame** → Contains **multiple columns and rows** of data with indexes.

### Easy Way to Remember

-> **Series → One Column**

-> **DataFrame → Multiple Columns + Rows**


# Pandas — `read_csv()`

## What is `read_csv()`?

`pd.read_csv()` is used to **read a CSV file** and convert it into a Pandas **DataFrame**.

### Syntax

```python
pd.read_csv("file_name.csv")
```

### Example

```python
import pandas as pd

data = pd.read_csv("students.csv")

print(data)
```

### If File is in Another Folder

```python
data = pd.read_csv(r"C:\Users\YourName\Downloads\students.csv")
```

## What is CSV?

**CSV** stands for **Comma-Separated Values**.

It stores data in **rows and columns**.

### CSV vs Excel

| File    | Function          |
| ------- | ----------------- |
| `.csv`  | `pd.read_csv()`   |
| `.xlsx` | `pd.read_excel()` |

### Simple Definition

> **`pd.read_csv()` reads a CSV file and returns a DataFrame.**


# Pandas — CSV Modification Functions

## 1. `read_csv()`

Reads a CSV file into a DataFrame.

```python
data = pd.read_csv("students.csv")
```

## 2. `skiprows`

Skips one or more rows while reading a CSV file.

```python
data = pd.read_csv("students.csv", skiprows=2)
```

Here, the **first 2 rows are skipped**.

### Example

If the CSV contains:

```text
Student Data
Name,Age,Marks
Rahul,20,85
Priya,21,92
```

```python
data = pd.read_csv("students.csv", skiprows=1)
```

The first row (`Student Data`) is skipped, and Pandas reads:

```text
Name,Age,Marks
Rahul,20,85
Priya,21,92
```

## 3. `to_csv()`

Saves a DataFrame as a CSV file.

```python
data.to_csv("new_students.csv", index=False)
```

## 4. `drop()`

Removes rows or columns.

```python
data = data.drop("Age", axis=1)
```

## 5. `rename()`

Changes column names.

```python
data = data.rename(columns={"Name": "Student_Name"})
```

## 6. `replace()`

Replaces values.

```python
data = data.replace("Kolkata", "Siliguri")
```

## 7. `fillna()`

Fills missing values.

```python
data["Age"] = data["Age"].fillna(0)
```

## 8. `dropna()`

Removes rows containing missing values.

```python
data = data.dropna()
```

## 9. `sort_values()`

Sorts the data.

```python
data = data.sort_values("Marks")
```

### Descending Order

```python
data = data.sort_values("Marks", ascending=False)
```

## 10. `astype()`

Changes the data type.

```python
data["Age"] = data["Age"].astype(int)
```

## 11. `apply()`

Applies a function to values.

```python
data["Marks"] = data["Marks"].apply(lambda x: x + 5)
```

## 12. `drop_duplicates()`

Removes duplicate rows.

```python
data = data.drop_duplicates()
```

## 13. `insert()`

Adds a new column at a specific position.

```python
data.insert(1, "Gender", ["M", "F", "M", "F", "M"])
```

## 14. Add a New Column

```python
data["Pass"] = data["Marks"] >= 40
```

## 15. Modify a Column

```python
data["Marks"] = data["Marks"] + 5
```

## 16. Modify a Specific Value

```python
data.loc[0, "Marks"] = 90
```

## 17. `query()`

Filters rows using a condition.

```python
data = data.query("Marks > 80")
```

## 18. `set_index()`

Sets a column as the index.

```python
data = data.set_index("Name")
```

## 19. `reset_index()`

Resets the index.

```python
data = data.reset_index()
```

# Most Important Functions

For beginner-level Pandas, focus first on:

* `read_csv()`
* `skiprows`
* `to_csv()`
* `drop()`
* `rename()`
* `replace()`
* `fillna()`
* `dropna()`
* `sort_values()`
* `astype()`
* `drop_duplicates()`
* `insert()`
* `query()`
* `set_index()`
* `reset_index()`
