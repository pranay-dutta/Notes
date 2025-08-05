**Topic:** [[Array]]
**Problem:**  [[Find First and Last Position of Element in Sorted Array]]
**Last Modified:**  `2025-08-06 00:22`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: 

 
```cpp
vector<int> searchRange(vector<int>& nums, int target) {
	int f = -1, l = -1;
	int n = nums.size();
	for(int i=0; i <n; i++) {
		int x = nums[i];

		if(x==target && f == -1) f = i;  
		else if(x==target && f != -1) l = i;
	}
	if(f != -1 && l == -1) return {f, f};

	return {f, l};
	
}
```
