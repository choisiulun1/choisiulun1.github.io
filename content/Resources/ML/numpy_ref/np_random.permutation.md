---
tags:
  - ML
  - numpy
aliases:
---
# Usage

The `np.random.permutation` function in NumPy is used to randomly permute a sequence or return a permuted range. When you pass an integer to `np.random.permutation` , it returns a randomly permuted array of integers from `0` to `n-1` where `n` is the integer provided.

```python
np.random.permutation(x)
```

- **`x`**: Can be an integer or an array.
  - If `x` is an integer, it returns a permutation of integers from `0` to `x-1`.
  - If `x` is an array, it returns a permuted array of `x`.

## Example 1: Permuting a Range of Integers

```python
import numpy as np

# Generate a random permutation of integers from 0 to 9
permutation = np.random.permutation(10)
print(permutation)
```

**Output** (Example):
```plaintext
[3 1 7 4 2 8 6 0 9 5]
```

In this example, `np.random.permutation(10)` returns a random ordering of the integers from `0` to `9`.

## Example 2: Shuffling Rows of a DataFrame

```python
import pandas as pd
import numpy as np

# Create a simple DataFrame
data = {
    'A': [1, 2, 3, 4],
    'B': [5, 6, 7, 8],
    'C': [9, 10, 11, 12]
}

df = pd.DataFrame(data)
print("Original DataFrame:")
print(df)

# Shuffle the rows
shuffled_indices = np.random.permutation(len(df))
shuffled_df = df.iloc[shuffled_indices]
print("\nShuffled DataFrame:")
print(shuffled_df)
```

**Output** (Example):
```plaintext
Original DataFrame:
   A  B   C
0  1  5   9
1  2  6  10
2  3  7  11
3  4  8  12

Shuffled DataFrame:
   A  B   C
3  4  8  12
0  1  5   9
2  3  7  11
1  2  6  10
```

>[!warning]
>`np.random.permutation` operates by permuting along the first (or highest) dimension of an array when the input is an array. It essentially shuffles the elements along this dimension, leaving the sub-arrays intact.

```python
import numpy as np

# Create a 2D array (3x3 matrix)
matrix = np.array([[1, 2, 3],
                   [4, 5, 6],
                   [7, 8, 9]])

print("Original Matrix:")
print(matrix)

# Apply np.random.permutation
shuffled_matrix = np.random.permutation(matrix)
print("\nShuffled Matrix:")
print(shuffled_matrix)

```

**Output** (Example):
```
Original Matrix:
[[1 2 3]
 [4 5 6]
 [7 8 9]]

Shuffled Matrix:
[[7 8 9]
 [4 5 6]
 [1 2 3]]
```