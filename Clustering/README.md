# 🐼 Pandas 101 — Beginner to Intermediate Guide

A complete introduction to **Pandas**, the most popular Python library for data analysis and manipulation.

This guide covers:
- Core concepts
- DataFrame operations
- Filtering techniques
- CRUD operations
- Data cleaning
- Data analysis
- Saving data

---

## 📦 What Is Pandas?

**Pandas** is an open-source Python library used for:

- 📊 Data analysis
- 🧹 Data cleaning
- 🔄 Data transformation
- 📁 Working with CSV, Excel, SQL, JSON, APIs

It is built on top of **NumPy**, which makes it fast and efficient for handling structured data.

### ✅ Why Use Pandas?
- Simple and readable syntax
- Handles large datasets efficiently
- Works like Excel but programmable
- Powerful grouping and filtering
- Excellent integration with ML libraries

---

## 🧱 Core Data Structures

Pandas mainly uses two data structures:

### 1️⃣ Series
A **one-dimensional labeled array** (like a single column in Excel).

```python
import pandas as pd

s = pd.Series([10, 20, 30])
print(s)
````

---

### 2️⃣ DataFrame

A **two-dimensional table** with labeled rows and columns (like a spreadsheet or SQL table).

Each column can contain different data types.

---

## 📊 Creating a DataFrame

```python
import pandas as pd

data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'Country': ['USA', 'Canada', 'UK']
}

df = pd.DataFrame(data)
print(df)
```

**Output:**

```
     Name  Age Country
0   Alice   25     USA
1     Bob   30  Canada
2 Charlie   35      UK
```

---

## 📥 Loading Data

```python
df = pd.read_csv('data.csv')        # Load CSV file
df = pd.read_excel('data.xlsx')     # Load Excel file
df = pd.DataFrame(data_dict)        # From dictionary
```

---

## 🔍 Exploring Data

```python
df.head()        # First 5 rows
df.tail()        # Last 5 rows
df.info()        # Data types and non-null counts
df.describe()    # Statistical summary
df.columns       # Column names
df.index         # Row indices
```

---

## 🎯 Accessing & Filtering Data

### 📌 Basic Access

```python
df['Age']                  # Single column
df[['Name', 'Age']]        # Multiple columns
df.iloc[0]                 # First row by position
df.loc[0]                  # First row by label
```

---

### 🔎 Conditional Filtering

```python
df[df['Age'] > 30]
df[df['Country'] == 'USA']
df[(df['Age'] > 25) & (df['Country'] == 'UK')]
```

---

### 🚀 Advanced Filtering

```python
df[df['Name'].str.startswith('A')]
df[df['Country'].isin(['USA', 'UK'])]
df[~df['Country'].isin(['Canada'])]
```

---

## 🔁 CRUD Operations in Pandas

### ➕ Create (Insert Rows)

```python
new_row = pd.DataFrame([{
    'Name': 'Diana',
    'Age': 28,
    'Country': 'Germany'
}])

df = pd.concat([df, new_row], ignore_index=True)
```

---

### 🔎 Read (Retrieve Data)

```python
df.loc[df['Name'] == 'Alice']
df.iloc[2]
```

---

### ✏️ Update (Modify Data)

```python
df.loc[df['Name'] == 'Bob', 'Age'] = 31
df['Country'] = df['Country'].str.upper()
```

---

### ❌ Delete (Remove Data)

```python
df = df.drop(2, axis=0)
df = df[df['Name'] != 'Alice']
df = df.drop('Age', axis=1)
```

---

## 🧹 Data Cleaning

```python
df.isnull().sum()
df.dropna(inplace=True)
df.fillna({'Age': 0}, inplace=True)
df.rename(columns={'Age': 'Years'}, inplace=True)
df['Years'] = df['Years'].astype(float)
```

---

## 📊 Data Analysis

```python
df['Country'].value_counts()
df.groupby('Country')['Age'].mean()
df.sort_values(by='Age', ascending=False)
```

---

## 💾 Saving Data

```python
df.to_csv('cleaned_data.csv', index=False)
df.to_excel('output.xlsx', index=False)
```

---

## 🎯 Final Thoughts

Pandas is an essential skill for:

* Data Science
* Machine Learning
* Web Development (Backend analytics)
* Research & Business Intelligence

Mastering Pandas will significantly improve your ability to work with real-world datasets efficiently.

---

⭐ If this guide helped you, consider starring your repository!

```
