**Topic:** [[Kadane's Algorithm]] [[Dynamic Programing]]
**Problem:**  [[Maximum Subarray]]
**Last Modified:**  `2025-07-19 14:03`

 $TC: O(n^2)$
 $SC: O(1)$

---
##### **Intuition**: use two loops and generate all subarray sums

```cpp
int maxSubArray(vector<int>& nums) {
	int n = nums.size();
	int maxSum = nums[0];

	for (int i = 0; i < n; i++) {
		int sum = 0;
		
		for (int j = i; j < n; j++) {
			sum += nums[j];
			maxSum = max(sum, maxSum);
		}
	}
	return maxSum;
}
```
