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
- Use `metric()` for sales, profit, tot
- Use `json()` for structured data.

# Chapter 4

# Streamlit: `st.set_page_config()`

`st.set_page_config()` is used to configure the page settings and layout of a Streamlit app.

## Parameters

- `page_title`: Sets the browser tab title.
- `page_icon`: Sets the browser tab icon.
- `layout="wide"`: Uses more horizontal space.
- `layout="centered"`: Keeps content centered.
- `initial_sidebar_state="expanded"`: Opens the sidebar initially.
- `initial_sidebar_state="collapsed"`: Closes the sidebar initially.
- `menu_items`: Adds options like Help, Report a bug, and About.

## Example

```python
import streamlit as st

st.set_page_config(
    page_title="Sales Dashboard",
    page_icon="📊",
    layout="wide",
    initial_sidebar_state="expanded",
    menu_items={
        "About": "My Sales Dashboard"
    }
)

st.title("Sales Analysis")
```

**Note:** Write `st.set_page_config()` before other Streamlit UI commands.

# Streamlit: `st.sidebar`

`st.sidebar` is used to display UI elements on the sidebar of a Streamlit app.

## Uses
- `st.sidebar.title()` – Adds a sidebar title.
- `st.sidebar.text_input()` – Takes text input.
- `st.sidebar.selectbox()` – Creates a dropdown menu.
- `st.sidebar.button()` – Creates a button.
- `st.sidebar.number_input()` – Takes numerical input.

## Example

```python
import streamlit as st

st.sidebar.title("Menu")

name = st.sidebar.text_input("Enter Name")

if st.sidebar.button("Submit"):
    st.write("Hello", name)
```

**Note:** Sidebar elements appear on the side, while `st.write()` displays output in the main page.

# Streamlit: `st.columns()`

## 1. Introduction

`st.columns()` is used to arrange content side by side in a Streamlit app.

## 2. Create Two Columns

```python
import streamlit as st

col1, col2 = st.columns(2)

with col1:
    st.write("Python")

with col2:
    st.write("SQL")
```

- `st.columns(2)` creates two columns.
- `with col1:` displays content in the first column.
- `with col2:` displays content in the second column.

## 3. Create Multiple Columns

```python
col1, col2, col3 = st.columns(3)
```

This creates three columns.

## 4. Different Column Widths

```python
col1, col2 = st.columns([2, 1])
```

- First column is twice as wide as the second.
- Numbers represent relative widths.

## 5. Gap Between Columns

```python
col1, col2 = st.columns(2, gap="large")
```

The `gap` parameter controls the space between columns.

- `"small"` – Small gap
- `"medium"` – Medium gap (default)
- `"large"` – Large gap

## 6. Vertical Alignment

```python
col1, col2 = st.columns(
    2,
    vertical_alignment="center"
)
```

Aligns column content vertically.

Options:
- `"top"`
- `"center"`
- `"bottom"`

## 7. Column Border

```python
col1, col2 = st.columns(2, border=True)
```

Adds a border around each column.

## 8. Create Columns Using a Loop

```python
cols = st.columns(5)

for i, col in enumerate(cols):
    with col:
        st.write(f"Column {i + 1}")
```

- Creates five columns automatically.
- `enumerate()` provides the index and column.
- Useful when creating many columns.

## 9. Dynamic Columns

```python
n = st.number_input(
    "Number of columns",
    min_value=1,
    max_value=10,
    value=3
)

cols = st.columns(int(n))

for i, col in enumerate(cols):
    with col:
        st.write(f"Column {i + 1}")
```

The user can choose how many columns to create.

## 10. Dashboard Example

```python
import streamlit as st

st.title("Sales Dashboard")

col1, col2, col3 = st.columns(3)

with col1:
    st.metric("Sales", "₹50,000")

with col2:
    st.metric("Profit", "₹10,000")

with col3:
    st.metric("Customers", "120")
```

This displays three metrics side by side.

## Important Points

- `st.columns()` creates a horizontal layout.
- Use `with col:` to place elements inside a column.
- Use width ratios to control column sizes.
- Use `gap` to control spacing.
- Use `vertical_alignment` to align content.
- Use `border=True` to add borders.
- Use loops for multiple columns.

# Streamlit Tabs and Expander

## 1. Tabs (`st.tabs()`)

- `st.tabs()` is used to divide content into separate tabs.
- Users can click a tab to view its content.
- It helps organize different categories in one page.

**Syntax:**
```python
tab1, tab2 = st.tabs(["Python", "C++"])

with tab1:
    st.write("Python Syllabus")

with tab2:
    st.write("C++ Syllabus")
```

**Use:** To separate Python, C++, and ML syllabuses.

## 2. Expander (`st.expander()`)

- `st.expander()` is used to hide and show content.
- Users can click the expander to open or close the content.
- It helps keep a page clean and organized.
- The content inside the `with` block appears inside the expander.

**Syntax:**
```python
import streamlit as st

with st.expander("Python Syllabus"):
    st.write("Variables")
    st.write("Loops")
    st.write("Functions")
```

**Use:** To show or hide the topics of a syllabus.

## Difference Between Tabs and Expander

| Tabs | Expander |
|---|---|
| Divides content into tabs | Hides and shows content |
| Click to switch categories | Click to open or close |
| Uses `st.tabs()` | Uses `st.expander()` |
| Example: Python, C++, ML | Example: Python topics |


# Streamlit Container (`st.container()`)

- `st.container()` groups multiple elements in one section.
- It helps organize content in a Streamlit app.
- We can put text, buttons, charts, and other elements inside it.
- It does not automatically add a visible border or background.

**Syntax:**
```python
with st.container():
    st.title("Student Dashboard")
    st.write("Welcome")
    st.button("Start")
```

**Use:** To organize related elements into a group.

# Streamlit Form (`st.form()`)

- `st.form()` creates a form to collect user inputs.
- It groups multiple input fields together.
- Inputs are submitted together using `st.form_submit_button()`.
- The app does not rerun for every input change inside the form.

**Example:**
```python
import streamlit as st

with st.form("my_form"):
    name = st.text_input("Enter Name")
    submit = st.form_submit_button("Submit")

if submit:
    st.write("Name:", name)
```

**Uses:** Registration forms, login forms, and feedback forms.
