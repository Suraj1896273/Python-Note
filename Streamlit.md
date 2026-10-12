# Chapter 1

# Streamlit: Title, Header and Subheader

## 1. `st.title()`
- Displays the main title of an app.

```python
st.title("iPhone Sales Dashboard")
```

## 2. `st.header()`
- Displays a main section heading.

```python
st.header("Sales Analysis")
```

## 3. `st.subheader()`
- Displays a smaller heading inside a section.

```python
st.subheader("Model-wise Sales")
```

## Complete Example

```python
import streamlit as st

# Streamlit: write(), markdown() and text()

## 1. `st.write()`
- Displays text, numbers, lists, DataFrames, and other objects.

```python
st.write("Hello World")
st.write(100)
```

## 2. `st.markdown()`
- Displays formatted text using Markdown syntax.
- Supports headings, bold, italic, and tables.

```python
st.markdown("# Hello World")
st.markdown("**Welcome to Streamlit**")
```

## 3. `st.text()`
- Displays plain text without Markdown formatting.

```python
st.text("Hello World")
```

## Difference
- `st.write()` → Displays different types of data.
- `st.markdown()` → Displays formatted text.
- `st.text()` → Displays plain text.

# Streamlit: Success, Error, Warning and Info

## 1. `st.success()`
- Displays a success message.
- Used when a task is completed successfully.
- It usually appears in a green box.

```python
import streamlit as st

st.success("Data saved successfully!")
```

## 2. `st.error()`
- Displays an error message.
- Used when an error occurs.
- It usually appears in a red box.

```python
st.error("File not found!")
```

## 3. `st.warning()`
- Displays a warning message.
- Used to alert users about a possible problem.
- It usually appears in a yellow or orange box.

```python
st.warning("Please check your data!")
```

## 4. `st.info()`
- Displays an information message.
- Used to provide useful information or instructions.
- It usually appears in a blue box.

```python
st.info("Please upload your CSV file.")
```

## Complete Example

```python
import streamlit as st

st.success("Task completed!")
st.error("Something went wrong!")
st.warning("Please check your input!")
st.info("Welcome to the dashboard!")
```

## Difference

- `st.success()` → Success message
- `st.error()` → Error message
- `st.warning()` → Warning message
- `st.info()` → Information message


st.title("iPhone Sales Dashboard")
st.header("Sales Analysis")
st.subheader("Model-wise Sales")
```


## Difference
- `st.title()` → Main app title
- `st.header()` → Main section heading
- `st.subheader()` → Subsection headin

# Chapter 2

# Streamlit Input and Button

## 1. `st.text_input()`
- Takes text input from the user.
- Example: Name, email, city.

```python
name = st.text_input("Enter your name")
```

## 2. `st.number_input()`
- Takes numerical input from the user.
- Example: Age, marks, price.

```python
marks = st.number_input("Enter marks", 0, 100)
```

## 3. `st.button()`
- Creates a button.
- Executes code when the user clicks it.

```python
if st.button("Submit"):
    st.write("Submitted successfully!")
```

## Example

```python
import streamlit as st

name = st.text_input("Enter name")
marks = st.number_input("Enter marks", 0, 100)

if st.button("Analyze"):
    st.write("Name:", name)
    st.write("Marks:", marks)
```

# Streamlit Input Functions

## 1. `st.checkbox()`
- Used to select or unselect an option.
- Returns `True` if checked, otherwise `False`.

```python
present = st.checkbox("Student Present")
```

## 2. `st.radio()`
- Used to select only one option from multiple options.

```python
dept = st.radio("Choose Department", ["CSE", "IT", "ECE"])
```

## 3. `st.date_input()`
- Used to select a date from a calendar.

```python
date = st.date_input("Select Date")
```

## Quick Revision
- `checkbox()` → Check or uncheck
- `radio()` → Select one option
- `date_input()` → Select a date

# If Condition in Streamlit

- `if` checks a condition.
- If the condition is `True`, the code inside `if` runs.
- `file is not None` means a file has been uploaded.

```python
file = st.file_uploader("Upload CSV")

if file is not None:
    st.write("File uploaded successfully!")
```

**Remember:**
- No file → Condition is `False`.
- File uploaded → Condition is `True`.

  # Streamlit Data Display

## 1. `st.dataframe()`

- Displays data in an interactive table.
- Users can scroll and sort the data.
- Best for large datasets.

```python
import streamlit as st
import pandas as pd

df = pd.DataFrame({
    "Name": ["Rahul", "Priya"],
    "Marks": [80, 90]
})

st.dataframe(df)
```

## 2. `st.table()`

- Displays data in a simple, static table.
- Users cannot interact with it like `st.dataframe()`.
- Best for small datasets.

```python
st.table(df)
```

## 3. `st.metric()`

- Displays an important number or KPI.
- `label` = Name of the metric.
- `value` = Current value.
- `delta` = Change compared with another value.

```python
st.metric(
    label="Total Sales",
    value=50000,
    delta=5000
)
```

**Output meaning:**
- Total Sales = 50,000
- Delta = +5,000

**Note:** The values are manually provided here. You can calculate them from your dataset.

## 4. `st.json()`

- Displays a dictionary or JSON-like data in a formatted structure.
- Useful for showing structured information.
- It does not save data to a database.

```python
student = {
    "Name": "Rahul",
    "Age": 20,
    "Marks": 90
}

st.json(student)
```

## Quick Summary

| Method | Use |
|---|---|
| `st.dataframe()` | Interactive data table |
| `st.table()` | Static data table |
| `st.metric()` | Important numbers or KPIs |
| `st.json()` | Formatted dictionary or JSON data |

## Remember

- Use `dataframe()` for large datasets.
- Use `table()` for small tables.
- Use `metric()` for sales, profit, total students, or average marks.
- Use `json()` for structured data.
