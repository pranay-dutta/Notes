**Topic:** [[4 - Index/Two Pointers]]
**Problem:**  [[Move Zeros]]
**Last Modified:**  `2025-05-12 15:15`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: Slow pointer runs if **x** is not zero. It gets **swapped** with **fast pointer's value**

 
```cpp
slow = 0
for(fast=0, n) {
	if(nums[fast]) swap(nums[fast], nums[slow++]) //0, 1, 0, 2, 3 
	//when fast finds a non-zero value it swaps with slow
}

```

