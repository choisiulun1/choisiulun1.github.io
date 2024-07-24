---
tags: [ACM, Purple Book]
aliases: []
---
## Output floating point number
```c
#include<stdio.h>
int main()
{
	printf("%.1f\n", 8.0/5.0);
	return 0;
}
```
- Experiment 1: change `%.1f` into `%.2f`
	- result output changed from `1.6` to `1.60`
- Experiment 2:change `8.0/5.0` to `8/5`
	- result output changed from `1.6` to `0.0`
 - Experiment 3:change `%.1f` to `%d` without changing `8.0/5.0`
	 - result output changed from `1.6` to `-1717986918`
	 - Reason see : [[Correct format specifier for double in printf|Argument Promotion]]