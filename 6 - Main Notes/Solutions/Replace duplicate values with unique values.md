**Topic:**  [[4 - Index/Two Pointers]]
**Problem:**  [[Remove Duplicates from Sorted Array]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: if nums[i] & nums[j] is same ***j*** will move. If unique found move with ***i++*** and  replace it with nums[j] 

 
```cpp
i = 0, j = 1
while(j < n) {
	if (nums[i] != nums[j]) //if unique found
		nums[++i] = nums[j];
	else j++;           //other wise search for unique
}
```

