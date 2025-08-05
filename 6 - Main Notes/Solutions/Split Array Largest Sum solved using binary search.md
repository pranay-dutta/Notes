**Topic:** [[Binary Search]] [[Binary Search on Answer]]
**Problem:**  [[Split Array Largest Sum]]
**Last Modified:**  `2025-08-05 19:31`

 $TC: O(n \log n)$
 $SC: O(1)$

---
##### **Intuition**: reduce the Largest sum and which is Accumulation of whole array and the smallest sum would be Max element

 
```cpp
bool isSplitPossible(vector<int>& nums, int maxAllowedSum, int k) {
	int sum = 0;
	for(int i = 0; i < nums.size(); i++) {

		if(sum + nums[i] > maxAllowedSum) { //agar nums[i] ko le lia toh, will it exceed maxAllowedSum
			k--;
			sum = nums[i];
			if(k == 0) return false;
		} else {
			sum += nums[i];
		}
	}
	return true;
}
int splitArray(vector<int>& nums, int k) {
	int l = *max_element(begin(nums), end(nums));
	int r = accumulate(begin(nums), end(nums), 0);

	int ans = 0;
	while (l <= r) {
		int mid = l + (r - l) / 2;
		if (isSplitPossible(nums, mid, k)) {
			r = mid - 1;
			ans = mid;
		} else {
			l = mid + 1;
		}
	}
	return ans;
}
```

