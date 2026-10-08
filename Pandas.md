# Pandas Complete Notes

# Level 1: Pandas Basics

## 1. What is Pandas?

**Pandas** is a Python library used for:

* Data manipulation
* Data analysis
* Data cleaning
* Working with structured data
* Reading and writing files

Pandas helps us work with data in the form of **tables**, similar to Excel spreadsheets.

### Simple Definition

> **Pandas is a Python library used to store, clean, analyze, and manipulate structured data.**

---

# 2. Installing Pandas

If Pandas is not installed, use:

```bash
pip install pandas
```

---

# 3. Importing Pandas

We normally import Pandas using the alias `pd`.

```python
import pandas as pd
```

Now we can use:

```python
pd.Series()
pd.DataFrame()
pd.read_csv()
```

---

# 4. Pandas Series

## What is a Series?

A **Series** is a **one-dimensional** data structure.

It stores:

* Values
* Index

### Simple Definition

> **Series → One-dimensional labeled data structure.**

The uploaded notes also summarize it as **one column of data with an index**.

---

# 5. Creating a Series

Use:

```python
pd.Series()
```

Example:

```python
import pandas as pd

s = pd.Series(["Ind", "Aus", "NZ"])

print(s)
```

Output:

```text
0    Ind
1    Aus
2     NZ
dtype: object
```

Here:

```text
0, 1, 2 → Index
Ind, Aus, NZ → Values
```

---

# 6. Series with Custom Index

```python
s = pd.Series(
    ["Ind", "Aus", "NZ"],
    index=["A", "B", "C"]
)

print(s)
```

Output:

```text
A    Ind
B    Aus
C     NZ
```

---

# 7. Pandas DataFrame

## What is a DataFrame?

A **DataFrame** is a **two-dimensional** data structure.

It contains:

* Rows
* Columns
* Index
* Values

It is similar to an Excel spreadsheet or database table.

### Simple Definition

> **DataFrame → Two-dimensional labeled data structure containing rows and columns.**

### Easy Remember

```text
Series    → One column
DataFrame → Multiple rows + columns
```

---

# 8. Creating a DataFrame

Use:

```python
pd.DataFrame()
```

Example:

```python
import pandas as pd

data = {
    "Name": ["Rahul", "Priya", "Amit"],
    "Age": [25, 23, 28],
    "City": ["Kolkata", "Siliguri", "Delhi"]
}

df = pd.DataFrame(data)

print(df)
```

Output:

```text
    Name  Age      City
0  Rahul   25   Kolkata
1  Priya   23  Siliguri
2   Amit   28     Delhi
```

---

# 9. Creating DataFrame from Dictionary

A dictionary is one of the most common ways to create a DataFrame.

```python
data = {
    "Name": ["Rahul", "Priya", "Amit"],
    "Age": [25, 23, 28],
    "City": ["Kolkata", "Siliguri", "Delhi"]
}

df = pd.DataFrame(data)
```

Here:

```text
Dictionary key   → Column name
Dictionary value → Column data
```

The uploaded notes use the same dictionary → DataFrame approach.

---

# 10. Creating DataFrame from List

A list of lists can also be converted into a DataFrame.

```python
data = [
    ["Rahul", 25, "Kolkata"],
    ["Priya", 23, "Siliguri"],
    ["Amit", 28, "Delhi"]
]

df = pd.DataFrame(
    data,
    columns=["Name", "Age", "City"]
)

print(df)
```

Output:

```text
    Name  Age      City
0  Rahul   25   Kolkata
1  Priya   23  Siliguri
2   Amit   28     Delhi
```

---

# 11. Creating DataFrame from NumPy Array

We can create a DataFrame from a NumPy array.

```python
import numpy as np
import pandas as pd

data = np.array([
    [101, "Rahul"],
    [102, "Priya"],
    [103, "Amit"]
])

df = pd.DataFrame(
    data,
    columns=["ID", "Name"]
)

print(df)
```

---

# 12. Index

An **index** identifies the rows of a DataFrame.

Default index:

```text
0
1
2
3
```

Example:

```python
df.index
```

We can also create a custom index:

```python
df = pd.DataFrame(
    data,
    index=["A", "B", "C"]
)
```

---

# 13. Columns

`columns` gives the column names.

```python
df.columns
```

Example output:

```text
Index(['Name', 'Age', 'City'], dtype='object')
```

---

# 14. Shape

`shape` tells us the number of:

```text
rows × columns
```

Example:

```python
df.shape
```

Output:

```text
(3, 3)
```

Meaning:

```text
3 rows
3 columns
```

---

# 15. Size

`size` tells us the **total number of elements**.

```python
df.size
```

If:

```text
3 rows × 3 columns
```

then:

```text
size = 9
```

---

# 16. ndim

`ndim` tells us the number of dimensions.

For a DataFrame:

```python
df.ndim
```

Output:

```text
2
```

For a Series:

```python
s.ndim
```

Output:

```text
1
```

Remember:

```text
Series    → ndim = 1
DataFrame → ndim = 2
```

---

# 17. Data Types

`dtypes` tells us the data type of each column.

```python
df.dtypes
```

Example:

```text
Name    object
Age      int64
```

Common types:

```text
int64
float64
object
bool
```

---

# 18. head()

`head()` displays the first rows.

```python
df.head()
```

By default it shows the first **5 rows**.

We can specify the number:

```python
df.head(3)
```

→ First 3 rows.

---

# 19. tail()

`tail()` displays the last rows.

```python
df.tail()
```

By default it shows the last **5 rows**.

```python
df.tail(3)
```

→ Last 3 rows.

---

# 20. info()

`info()` gives information about the DataFrame.

```python
df.info()
```

It provides information such as:

* Number of rows
* Column names
* Non-null values
* Data types
* Memory usage

---

# 21. describe()

`describe()` gives statistical information about numerical columns.

```python
df.describe()
```

It commonly shows:

* count
* mean
* standard deviation
* minimum
* 25%
* 50%
* 75%
* maximum

---

# Level 1 Quick Revision

| Function     | Meaning               |
| ------------ | --------------------- |
| `head()`     | First rows            |
| `tail()`     | Last rows             |
| `shape`      | Rows × columns        |
| `size`       | Total elements        |
| `ndim`       | Number of dimensions  |
| `columns`    | Column names          |
| `index`      | Row indexes           |
| `dtypes`     | Data types            |
| `info()`     | DataFrame information |
| `describe()` | Statistical summary   |

---

# Level 2: Reading and Saving Data

# 22. Reading CSV

CSV means **Comma-Separated Values**.

Use:

```python
pd.read_csv()
```

Example:

```python
import pandas as pd

df = pd.read_csv("students.csv")

print(df)
```

`read_csv()` reads a CSV file and returns a DataFrame.

---

# 23. Reading CSV from Another Folder

```python
df = pd.read_csv(
    r"C:\Users\YourName\Downloads\students.csv"
)
```

Using `r` before the path helps handle Windows backslashes.

---

# 24. Saving DataFrame to CSV

Use:

```python
df.to_csv("students_new.csv")
```

Usually we don't want Pandas to save the DataFrame index:

```python
df.to_csv(
    "students_new.csv",
    index=False
)
```

### Remember

```text
read_csv() → CSV → DataFrame

to_csv()   → DataFrame → CSV
```

---

# 25. Reading Excel

Use:

```python
pd.read_excel()
```

Example:

```python
df = pd.read_excel("students.xlsx")
```

---

# 26. Saving to Excel

Use:

```python
df.to_excel("students_new.xlsx")
```

Without saving the index:

```python
df.to_excel(
    "students_new.xlsx",
    index=False
)
```

---

# 27. Reading JSON

JSON means **JavaScript Object Notation**.

Use:

```python
df = pd.read_json("students.json")
```

---

# 28. Saving to JSON

Use:

```python
df.to_json("students.json")
```

---

# 29. Important CSV Parameters

## `skiprows`

Skips rows while reading.

```python
df = pd.read_csv(
    "students.csv",
    skiprows=2
)
```

This skips the first 2 rows.

---

## `sep`

Used when the separator is not a comma.

Example:

```text
Name|Age|City
Rahul|20|Kolkata
Priya|21|Delhi
```

Read it using:

```python
df = pd.read_csv(
    "students.csv",
    sep="|"
)
```

For tab-separated data:

```python
df = pd.read_csv(
    "students.csv",
    sep="\t"
)
```

### Remember

```text
,  → comma
|  → pipe
\t → tab
;  → semicolon
```

---

# 30. `usecols`

Reads only selected columns.

```python
df = pd.read_csv(
    "students.csv",
    usecols=["Name", "Age"]
)
```

---

# 31. `nrows`

Reads only a specific number of rows.

```python
df = pd.read_csv(
    "students.csv",
    nrows=100
)
```

→ Reads only the first 100 rows.

---

# 32. `header`

Specifies which row contains column names.

```python
df = pd.read_csv(
    "students.csv",
    header=0
)
```

---

# 33. `dtype`

Specifies data types.

```python
df = pd.read_csv(
    "students.csv",
    dtype={"Age": "int32"}
)
```

---

# 34. Important Excel Parameters

## `sheet_name`

Select a particular sheet.

```python
df = pd.read_excel(
    "students.xlsx",
    sheet_name="Sheet1"
)
```

## `skiprows`

```python
df = pd.read_excel(
    "students.xlsx",
    skiprows=2
)
```

## `usecols`

```python
df = pd.read_excel(
    "students.xlsx",
    usecols=["Name", "Age"]
)
```

## `nrows`

```python
df = pd.read_excel(
    "students.xlsx",
    nrows=10
)
```

## `header`

```python
df = pd.read_excel(
    "students.xlsx",
    header=0
)
```

## `index_col`

Makes a column the index.

```python
df = pd.read_excel(
    "students.xlsx",
    index_col="ID"
)
```

The uploaded notes identify these as important Excel-reading parameters.

---

# 35. Reading Large Datasets

If a dataset is very large, loading the entire file into RAM may use a lot of memory.

## `chunksize`

Reads the dataset in smaller parts.

```python
chunks = pd.read_csv(
    "large_data.csv",
    chunksize=10000
)

for chunk in chunks:
    print(chunk)
```

Meaning:

```text
10000 rows
     ↓
10000 rows
     ↓
10000 rows
     ↓
...
```

`chunksize=10000` means Pandas reads **10,000 rows at a time**.

---

# 36. Large Dataset with usecols

Read only the columns required:

```python
df = pd.read_csv(
    "large_data.csv",
    usecols=["name", "age", "salary"]
)
```

This can reduce memory usage.

---

# 37. Large Dataset with dtype

```python
df = pd.read_csv(
    "large_data.csv",
    dtype={
        "age": "int32",
        "salary": "float32"
    }
)
```

Smaller data types can reduce memory usage.

---

# Level 2 Quick Revision

| Task             | Function          |
| ---------------- | ----------------- |
| Read CSV         | `pd.read_csv()`   |
| Save CSV         | `df.to_csv()`     |
| Read Excel       | `pd.read_excel()` |
| Save Excel       | `df.to_excel()`   |
| Read JSON        | `pd.read_json()`  |
| Save JSON        | `df.to_json()`    |
| Large data       | `chunksize`       |
| Selected columns | `usecols`         |
| Selected rows    | `nrows`           |
| Skip rows        | `skiprows`        |
| Separator        | `sep`             |
| Data type        | `dtype`           |

---

# Level 3: Selecting and Filtering Data

# 38. Selecting One Column

Use single square brackets:

```python
df["Name"]
```

This returns a **Series**.

```text
[] → one column → Series
```

---

# 39. Selecting Multiple Columns

Use double square brackets:

```python
df[["Name", "Age", "City"]]
```

This returns a **DataFrame**.

```text
[[]] → multiple columns → DataFrame
```

This distinction is emphasized in the uploaded notes.

---

# 40. Selecting Rows

We can filter rows using a condition.

```python
df[df["Age"] > 25]
```

This selects rows where:

```text
Age > 25
```

---

# 41. Selecting Rows and Specific Columns

```python
df[
    df["Age"] > 25
][
    ["Name", "City"]
]
```

This means:

```text
First → filter rows
Second → select columns
```

---

# 42. `loc`

`loc` is used to select rows and columns using **labels or conditions**.

### Syntax

```python
df.loc[row_condition, columns]
```

Example:

```python
df.loc[
    df["Age"] > 25,
    ["Name", "City"]
]
```

Meaning:

```text
Age > 25
+
Name and City columns
```

The source notes distinguish `df[condition]` as simple row filtering and `df.loc[condition, columns]` as row filtering plus column selection.

---

# 43. `iloc`

`iloc` means **Integer Location**.

It selects rows and columns using **integer positions**.

### Syntax

```python
df.iloc[row_position, column_position]
```

---

## Select One Row

```python
df.iloc[2]
```

Selects the **3rd row** because indexing starts from `0`.

```text
0 → 1st row
1 → 2nd row
2 → 3rd row
```

---

## Select Multiple Rows

```python
df.iloc[1:4]
```

Selects:

```text
2nd
3rd
4th
```

---

## Select One Column

```python
df.iloc[:, 2]
```

Meaning:

```text
: → all rows
2 → 3rd column
```

---

## Select Multiple Columns

```python
df.iloc[:, 1:4]
```

Selects columns 2, 3 and 4.

---

## Select One Row and One Column

```python
df.iloc[2, 3]
```

Means:

```text
3rd row
4th column
```

---

## Select Specific Rows

```python
df.iloc[[0, 2, 4]]
```

Selects:

```text
1st
3rd
5th
```

---

## Select Specific Columns

```python
df.iloc[:, [0, 2, 4]]
```

Selects:

```text
1st
3rd
5th
```

---

## Select Specific Rows and Columns

```python
df.iloc[[0, 2, 4], [1, 3]]
```

Means:

```text
Rows    → 1st, 3rd, 5th
Columns → 2nd, 4th
```

---

# 44. `loc` vs `iloc`

| Feature          | `loc`                | `iloc`   |
| ---------------- | -------------------- | -------- |
| Based on         | Label/condition      | Position |
| Integer position | Not its main purpose | Yes      |
| Condition        | Yes                  | No       |
| Select rows      | Yes                  | Yes      |
| Select columns   | Yes                  | Yes      |

### Easy Remember

```text
loc  → Label / condition
iloc → Integer position
```

The uploaded notes use this same distinction.

---

# 45. Boolean Indexing

Boolean indexing filters rows using conditions.

Example:

```python
df[df["Age"] > 25]
```

Only rows where the condition is `True` are selected.

---

# 46. Single Condition

Example:

```python
df[df["Age"] > 25]
```

Other examples:

```python
df[df["Salary"] >= 30000]

df[df["City"] == "Kolkata"]

df[df["Age"] != 25]
```

---

# 47. Multiple Conditions

## AND `&`

Both conditions must be true.

```python
df[
    (df["Age"] > 25) &
    (df["City"] == "Kolkata")
]
```

## OR `|`

At least one condition must be true.

```python
df[
    (df["Age"] > 25) |
    (df["City"] == "Kolkata")
]
```

## NOT `~`

Reverses the condition.

```python
df[
    ~(df["City"] == "Kolkata")
]
```

### Important

Always use parentheses:

```python
df[
    (condition1) &
    (condition2)
]
```

This matches the Boolean-indexing pattern in the source notes.

---

# 48. `isin()`

`isin()` checks whether a column contains any value from a given list.

### Syntax

```python
df[df["column"].isin([value1, value2])]
```

Example:

```python
df[
    df["payment_mode"].isin(["UPI", "EMI"])
]
```

This means:

```text
UPI OR EMI
```

The uploaded notes explicitly use `payment_mode` for this example.

### Easy Remember

```python
isin(["UPI", "EMI"])
```

→ Match **UPI OR EMI**

---

# 49. `between()`

`between()` checks whether values are inside a range.

### Syntax

```python
df["Age"].between(20, 30)
```

By default:

```text
20 ≤ Age ≤ 30
```

Both endpoints are included.

### Filter Rows

```python
df[
    df["Age"].between(20, 30)
]
```

The source notes describe `between()` as returning `True`/`False` for values within the given range.

---

# 50. `query()`

`query()` filters rows using a condition.

### Syntax

```python
df.query("condition")
```

Example:

```python
df.query("Age > 25")
```

Multiple conditions:

```python
df.query(
    "Age > 25 and City == 'Kolkata'"
)
```

### Remember

```text
query() = Find with condition
```

---

# 51. Selecting Specific Rows and Columns

Using `loc`:

```python
df.loc[
    [0, 2],
    ["Name", "Age"]
]
```

Using `iloc`:

```python
df.iloc[
    [0, 2],
    [0, 1]
]
```

Using a condition with `loc`:

```python
df.loc[
    df["Age"] > 25,
    ["Name", "City"]
]
```

---

# Level 3 Quick Revision

| Method               | Main Use                        |
| -------------------- | ------------------------------- |
| `df["Name"]`         | One column                      |
| `df[["Name","Age"]]` | Multiple columns                |
| `df[condition]`      | Filter rows                     |
| `loc`                | Label/condition based selection |
| `iloc`               | Position based selection        |
| Boolean indexing     | Filter using conditions         |
| `isin()`             | Match multiple values           |
| `between()`          | Filter a range                  |
| `query()`            | Filter using a query condition  |

---

## Level 4: Modifying Data

# 52. Adding a New Column

The easiest way to add a column is:

```python
df["Pass"] = df["Marks"] >= 40
```

This creates a new `Pass` column.

# `assign()` and `insert()` in Pandas

## 1. `assign()`

`assign()` is used to **add a new column** to a DataFrame.

### Syntax

```python
df = df.assign(column_name=values)
```

### Example

```python
df = df.assign(
    bonus=df["salary"] * 0.10
)
```

### Important

* Adds a new column.
* Normally adds it at the **end**.
* Returns a **new DataFrame**.

---

## 2. `insert()`

`insert()` is used to **add a column at a specific position**.

### Syntax

```python
df.insert(position, "column_name", values)
```

### Example

```python
df.insert(
    1,
    "bonus",
    df["salary"] * 0.10
)
```

Here, `1` means the column is inserted at **position 1**.

### Important

* Adds a new column.
* Allows us to choose the **position**.
* Directly modifies the original DataFrame.

---

## `assign()` vs `insert()`

| `assign()`            | `insert()`                   |
| --------------------- | ---------------------------- |
| Adds a column         | Adds a column                |
| Normally at the end   | At a specific position       |
| Returns new DataFrame | Modifies original DataFrame  |
| Easy for calculations | Useful when position matters |

### Easy Remember

```text
assign() → Add column
insert() → Add column at specific position
```


# 53. Creating a Column with Values

```python
df["Gender"] = ["M", "F", "M", "F"]
```

Example:

```python
df["Bonus"] = [1000, 2000, 1500, 2500]
```

---

# 54. Creating a Column Using Calculation

Suppose:

```python
df["Salary"]
```

We want to create a bonus equal to 10% of salary:

```python
df["Bonus"] = df["Salary"] * 0.10
```

We can also calculate total salary:

```python
df["Total"] = df["Salary"] + df["Bonus"]
```

---

# 55. Updating a Column

Suppose we want to increase every salary by 5%:

```python
df["Salary"] = df["Salary"] * 1.05
```

Or add 500:

```python
df["Salary"] = df["Salary"] + 500
```

The uploaded notes show the same direct column modification pattern.

---

# 56. Modifying a Specific Value

Use `loc`.

```python
df.loc[0, "Marks"] = 90
```

This changes the value of:

```text
Row → 0
Column → Marks
```

---

# 57. `assign()`

`assign()` is used to add new columns.

```python
df = df.assign(
    bonus=df["salary"] * 0.10
)
```

It returns a **new DataFrame**.

Multiple columns can be added:

```python
df = df.assign(
    bonus=df["salary"] * 0.10,
    total=df["salary"] + df["salary"] * 0.10
)
```

---

# 58. `insert()`

`insert()` adds a new column at a **specific position**.

### Syntax

```python
df.insert(
    position,
    "column_name",
    values
)
```

Example:

```python
df.insert(
    1,
    "Age",
    [20, 21, 22]
)
```

The new column is inserted at position `1`.

Unlike `assign()`, `insert()` directly modifies the original DataFrame.

---

# 59. `assign()` vs `insert()`

| Feature                    | `assign()` | `insert()`    |
| -------------------------- | ---------- | ------------- |
| Add column                 | Yes        | Yes           |
| Specific position          | No         | Yes           |
| Returns new DataFrame      | Yes        | No            |
| Modifies original directly | No         | Yes           |
| Multiple columns           | Yes        | One at a time |

### Easy Remember

```text
assign() → Add column
insert() → Add column at a position
```

---

# 60. Creating Columns Using Multiple Calculations

Example:

```python
df["Profit"] = (
    df["Units_Sold"] *
    df["Unit_Price"]
)
```

Another example:

```python
df["Total"] = (
    df["Salary"] +
    df["Bonus"]
)
```

This i
