# 1. What is Data Visualization?

## Definition

Data Visualization is the process of representing data in a visual form, such as charts, graphs, maps, and diagrams.

It helps us understand data easily and find useful information from large datasets.

## Example

Suppose we have the sales data of a shop:

| Product | Sales |
|---------|-------|
| Mobile | 50000 |
| Laptop | 80000 |
| Headphones | 20000 |
| Tablet | 40000 |

We can represent this data using a **Bar Chart**.

Instead of reading all the numbers, we can easily understand which product has the highest sales.

## Advantages of Data Visualization

1. Makes complex data easy to understand.
2. Helps identify patterns and trends.
3. Makes comparison easier.
4. Saves time in data analysis.
5. Helps in better decision-making.

## Common Types of Data Visualization

1. Bar Chart
2. Line Chart
3. Pie Chart
4. Histogram
5. Scatter Plot
6. Box Plot

# Matplotlib

## 1. Definition
Matplotlib is a Python library used to create graphs, charts, and plots for data visualization.

## 2. Importance of Matplotlib
- Helps to understand data easily.
- Makes large datasets easier to understand.
- Helps identify patterns and trends.
- Helps compare different data values.
- Useful in Data Analysis and Data Science.
- Helps to find outliers.

## 3. Features
- Easy to learn and use.
- Supports different types of charts.
- Allows customization of graphs.
- Works with NumPy and Pandas.
- Supports 2D and 3D visualization.



## 6. Types of Charts
1. **Line Chart:** Shows trends over time.
2. **Bar Chart:** Compares different categories.
3. **Pie Chart:** Shows percentages.
4. **Histogram:** Shows data distribution.
5. **Scatter Plot:** Shows the relationship between two variables.
6. **Box Plot:** Shows data spread and outliers.

## 7. Important Functions

| Function | Description |
|---|---|
| `plt.plot()` | Creates a line chart |
| `plt.bar()` | Creates a bar chart |
| `plt.pie()` | Creates a pie chart |
| `plt.hist()` | Creates a histogram |
| `plt.scatter()` | Creates a scatter plot |
| `plt.title()` | Adds a title |
| `plt.xlabel()` | Adds X-axis label |
| `plt.ylabel()` | Adds Y-axis label |
| `plt.legend()` | Displays legend |
| `plt.show()` | Displays the chart |
| `plt.savefig()` | Saves the chart |


# Matplotlib – Bar Plot

## 1. Definition
A Bar Plot is a type of graph used to compare different categories of data using rectangular bars.

**Example:** Comparing the ratings of Python, C, C++, and Java.

## 2. Importance
- Compares different categories.
- Identifies the highest and lowest values.
- Makes data easy to understand.
- Useful in sales and data analysis.

## 3. Basic Syntax

```python
plt.bar(x, height)
```

## 4. Important Functions and Parameters

| Function / Parameter | Description |
|---|---|
| `plt.bar()` | Creates a vertical bar plot. |
| `plt.barh()` | Creates a horizontal bar plot. |
| `plt.xlabel()` | Sets X-axis label. |
| `plt.ylabel()` | Sets Y-axis label. |
| `plt.title()` | Sets chart title. |
| `plt.show()` | Displays the chart. |
| `plt.legend()` | Displays the legend. |
| `plt.xticks()` | Sets X-axis tick labels. |
| `plt.yticks()` | Sets Y-axis tick labels. |
| `width` | Controls bar width. |
| `color` | Changes bar color. |
| `edgecolor` | Changes border color. |
| `linewidth` | Controls border thickness. |
| `alpha` | Controls transparency. |
| `label` | Gives a name to the data series. |

## 5. Legend (`plt.legend()`)

**Definition:** Legend identifies different data series in a graph.

```python
plt.bar(x, y, label='Python')
plt.legend(loc='upper right')
```

## 6. Multiple Bar Graph

**Definition:** A Multiple Bar Graph compares two or more datasets across the same categories.

- `np.arange()` – Creates numerical positions.
- `width` – Controls bar width.
- `p - width/2` – Moves bars left.
- `p + width/2` – Moves bars right.
- `plt.xticks()` – Sets category names.

