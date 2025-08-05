**Topic:** [[Binary Search]]
**Problem:**  [[Find First and Last Position of Element in Sorted Array]]
**Last Modified:**  `2025-08-06 00:25`

 $TC: O(log\ n)$
 $SC: O(1)$

---
##### **Intuition**: if found the the element look for Lower answer to the left and Higher answer to the right

 
```cpp
int findLeft(vector<int>& nums, int target, int l, int r) {
	int s = -1;
	while (l <= r) {
		int mid = l + (r - l) / 2;

		if (target > nums[mid]) {
			l = mid + 1;
		} else if(nums[mid] == target) { // even if the index is found still look for lower index
			s = mid;
			r = mid - 1;
		} else { 
			r = mid - 1;
		}
	}
	return s;
}
int findRight(vector<int>& nums, int target, int l, int r) {
	int e = -1;
	
	while (l <= r) {
		int mid = l + (r - l) / 2;

		if (target > nums[mid]) {
			l = mid + 1;
		} else if(nums[mid] == target) { // even if the index is found still look for higher index
			e = mid;
			l = mid + 1;
		} else { 
			r = mid - 1;
		}
	}

	return e;
}
vector<int> searchRange(vector<int>& nums, int target) {
	int n = nums.size();

	int s = findLeft(nums, target, 0, n - 1);
	int e = findRight(nums, target, 0, n - 1);

	return {s, e};
}
```

