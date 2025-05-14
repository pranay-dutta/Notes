**Topic:**
**Problem:**  [[Two Sum]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n^2)$
 $SC: O(1)$

---
##### **Intuition**:  Brute force 

 
```cpp
for (i = 0; i < n) {
	for(j = 0; j <) {
		if(i != j && nums[i] + nums[j] == target) return {i, j}
	}
}
```
```