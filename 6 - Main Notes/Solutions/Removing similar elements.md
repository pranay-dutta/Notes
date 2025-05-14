**Topic:** 
**Problem:**  [[Remove Duplicates from Sorted Array]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n * k)$  
 $SC: O(1)$

---
##### **Intuition**:  Erase every non unique element once. Erase will happen **k** times which make this non efficient because **erase()** takes **O(n)** time. ***N x K*** times erase will happen. ***K*** is the number of non unique element
 

```cpp
for(i = 0; i<n -1) 
	if(nums[i] == nums[i+1]) //duplicate found
		nums.erase(nums.begin(), i+1); 
		i--, n--; //reducing size 

```

