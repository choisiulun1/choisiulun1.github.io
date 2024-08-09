---
tags:
  - ML
aliases:
---
# Split Dataset
```python
import numpy as np
def split_train_test(data, test_ratio):
	shuffled_indices = np.random.permutation(len(data))
	test_set_size = int(len(data) * test_ratio)
	test_indices = shuffled_indices[:test_set_size]
	train_indices = shuffled_indices[test_set_size:]
	return data.iloc[train_indices], data.iloc[test_indices]
```

Ref: ![[pandas_DataFrame.iloc#8. Using List Indices| DataFrame.iloc]]
![[np_random.permutation#Example 1 Permuting a Range of Integers| np.random.permutation]]

## Using Hash_ID to preserve the test set

```python
from zlib import crc32
import numpy as np
def test_set_check(identifier, test_ratio):
	return crc32(np.int64(identifier)) & 0xffffffff < test_ratio * 2**32

data = [i for i in range(10)]

# print(crc32(data)) not working , must be byte-like object

print(np.int64(data))

```
---
