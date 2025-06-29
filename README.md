# 📊 Pandas for Python: Complete Guide

## 🐼 What is Pandas?

**Pandas** is a powerful, open-source library in Python used for data manipulation and analysis. It provides two main data structures:
- `Series`: One-dimensional labeled arrays
- `DataFrame`: Two-dimensional labeled data structure with columns of potentially different types

---

## 🔍 Why Use Pandas?

- Easy handling of missing data
- Efficient and flexible data slicing and dicing
- Merging and joining datasets
- Data aggregation and group operations
- Powerful time-series functionality
- Input/output tools for CSV, Excel, SQL, JSON, etc.

---

## 🛠 Installation

```bash
pip install pandas
```

## 🧱 Core Data Structures

### 1. Series

```python
import pandas as pd

data = pd.Series([10, 20, 30], index=["a", "b", "c"])
print(data)
```

Output: 

```css
a    10
b    20
c    30
dtype: int64
```

### 2. DataFrame

```python
import pandas as pd

data = {
    "name": ["Alice", "Bob", "Charlie"],
    "age": [25, 30, 35]
}
df = pd.DataFrame(data)
print(df)
```

Output: 

```css
      name  age
0    Alice   25
1      Bob   30
2  Charlie   35
```

## 📁 I/O Operations

### Functions: 

```python
read_csv()                    # Load data from a CSV file
to_csv()                      # Write DataFrame to CSV
read_excel() / to_excel()     # Read/write Excel files
read_json() / to_json()       # Read/write JSON
read_sql() / to_sql()         # Read/write from SQL DB
read_html()                   # Parse HTML tables
```

Example:
```python
df = pd.read_csv("data.csv")      # Reads a CSV file
df.to_excel("output.xlsx")        # Saves DataFrame to Excel
```
## Data Inspection

```python
df.head()        # First 5 rows
df.tail()        # Last 5 rows
df.shape         # Rows, columns
df.info()        # Schema
df.describe()    # Summary statistics
df.columns       # Column labels
df.index         # Row labels
```

## 🧹 Data Cleaning

```python
df.dropna()                      # Drop missing values
df.fillna(0)                     # Fill missing with 0
df.replace("?", pd.NA)           # Replace values
df.astype({"age": int})          # Type conversion
```

## 🎯 Selection & Filtering

```python
df["name"]                     # Select column
df[["name", "age"]]            # Multiple columns
df.iloc[0]                     # First row by position
df.loc[0]                      # First row by label
df[df["age"] > 25]             # Filter rows
```

## 🔄 Sorting & Ranking

```python
df.sort_values("age")          # Sort by column
df.sort_index()                # Sort by index
df.rank()                      # Ranking
```

## 🔢 Aggregation & Grouping

```python
df.sum()
df.mean()
df.groupby("category").sum()
df.agg({"age": ["min", "max"]})
```

## 🔁 Merging & Joining

```python
pd.concat([df1, df2])           # Concatenate
pd.merge(df1, df2, on="id")     # Merge on key
```

## 🧱 Reshaping

```python
df.pivot_table(index="A", columns="B", values="C")
df.melt(id_vars=["id"], value_vars=["score1", "score2"])
df.stack()
df.unstack()
```

Output: 

```css
B    one  three  two
A                    
bar     0      5    0
foo     1      0    3
```

## 📆 Working with Dates

```python
df["date"] = pd.to_datetime(df["date"])
df["year"] = df["date"].dt.year
df.set_index("date").resample("M").mean()
```

## 🧪 Statistical Functions

```python
df.corr()
df.cov()
df.std()
```

## 🔁 Iteration

```python
for index, row in df.iterrows():
    print(row["name"], row["age"])
```

## ✅ Boolean Masking

```python
df[df["score"] > 80]
(df["age"] > 20) & (df["score"] > 50)
```

## 📈 Plotting (with matplotlib)

```python
import matplotlib.pyplot as plt

df["score"].plot(kind="line")
plt.show()
```

## 🧰 Utility Functions

```python
pd.isnull(df)
pd.notnull(df)
pd.get_dummies(df["category"])
df.duplicated()
df.drop_duplicates()
```
