**Topic:** [[Sliding Window]]
**Problem:**  [[Maximum Erasure Value]]
**Last Modified:**  `2025-08-06 01:26`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: slide the and shrink the window and keep track of values in map

 
```cpp
int maximumUniqueSubarray(vector<int>& nums) {
	int i = 0, j = 0, n = nums.size();
	unordered_map<int, int> mp;

	int maxSum = 0, sum = 0;

	while (j < n) {
		if (mp[nums[j]]) {
			mp[nums[i]]--;
			sum -= nums[i++];
		} else {
			mp[nums[j]]++;
			sum += nums[j++];
			maxSum = max(maxSum, sum);
		}
	}

	return maxSum;
}
```
