---
tags:
  - ML
  - pandas
aliases:
---
# Usage

`.iloc` is used to access rows and columns of a pandas DataFrame or Series by integer-based indexing.

** `.iloc` ** stands for "integer location" and allows you to select rows and columns by their integer position (i.e., their index) in the DataFrame.

---

```python
import pandas as pd

# Create a DataFrame
data = {
    'A': [1, 2, 3, 4],
    'B': [5, 6, 7, 8],
    'C': [9, 10, 11, 12]
}

df = pd.DataFrame(data)
print(df)
```

The DataFrame looks like this:

```plaintext
   A  B   C
0  1  5   9
1  2  6  10
2  3  7  11
3  4  8  12
```

## Examples of `.iloc`

### 1. Selecting a Single Row by Index

^8d3185

```python
# Select the first row
row_0 = df.iloc[0]
print(row_0)
```

Output:

```plaintext
A    1
B    5
C    9
Name: 0, dtype: int64
```

### 2. Selecting a Specific Value

```python
# Select the value at the first row and second column
value = df.iloc[0, 1]
print(value)
```

Output:

```plaintext
5
```

### 3. Selecting Multiple Rows

```python
# Select the first two rows
rows_0_1 = df.iloc[0:2]
print(rows_0_1)
```

Output:

```plaintext
   A  B   C
0  1  5   9
1  2  6  10
```

### 4. Selecting Specific Rows and Columns

```python
# Select rows 0 and 1, and columns 0 and 2
subset = df.iloc[0:2, [0, 2]]
print(subset)
```

Output:

```plaintext
   A  C
0  1  9
1  2 10
```

### 5. Selecting the Last Row

```python
# Select the last row
last_row = df.iloc[-1]
print(last_row)
```

Output:

```plaintext
A     4
B     8
C    12
Name: 3, dtype: int64
```

### 6. Selecting All Rows for a Specific Column

```python
# Select all rows for the first column
column_A = df.iloc[:, 0]
print(column_A)
```

Output:

```plaintext
0    1
1    2
2    3
3    4
Name: A, dtype: int64
```

### 7. Using Boolean Indexing

```python
# Select rows where the value in the first column is greater than 2
filtered_rows = df.iloc[df['A'] > 2, :]
print(filtered_rows)
```

Output:

```plaintext
   A  B   C
2  3  7  11
3  4  8  12
```

### 8. Using List Indices
```python
# Select rows given list indices
selected_rows = df.iloc[[0,2]]
print(selected_rows)
```