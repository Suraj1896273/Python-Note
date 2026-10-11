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
- `st.subheader()` → Subsection heading
