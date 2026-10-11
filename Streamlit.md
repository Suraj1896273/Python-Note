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

st.title("iPhone Sales Dashboard")
st.header("Sales Analysis")
st.subheader("Model-wise Sales")
```

## Difference
- `st.title()` → Main app title
- `st.header()` → Main section heading
- `st.subheader()` → Subsection heading
