**Topic:** [[Kadane's Algorithm]] [[Dynamic Programing]]
**Problem:**  [[Maximum Subarray]]
**Last Modified:**  `2025-07-19 14:03`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: on the problem page, 
#### In short: `why carry negativity if it doesn't benefit you`

```cpp
int maxSubArray(vector<int>& nums) {
	int n = nums.size();
	int maxSum = nums[0];
	int sum = 0;

	for(int& x: nums) {
		sum += x; //add current
		maxSum = max(maxSum, sum);

		if(sum < 0) sum = 0; //reset sum [don't carry negetive sum for next number]
		//or sum = max(sum, 0)
	}

	return maxSum;
}
```

