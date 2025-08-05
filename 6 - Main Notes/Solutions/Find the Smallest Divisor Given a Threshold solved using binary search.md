**Topic:** [[Binary Search]] [[Binary Search on Answer]]
**Problem:**  [[Find the Smallest Divisor Given a Threshold]]
**Last Modified:**  `2025-08-06 02:16`

 $TC: O(n \log n)$
 $SC: O(1)$

---
##### **Intuition**: take the **max element** as the r and l as 1 and do binary search

 
```cpp
bool isBetweenThreshold(vector<int>& nums, int divisor, int threshold) {
	int sum = 0;
	for(int x: nums) {
		sum += (x + divisor - 1) / divisor; //ceil function
		if(sum > threshold) return false;
	}
	return true;
}
int smallestDivisor(vector<int>& nums, int threshold) {
	int l = 1, r = *max_element(begin(nums), end(nums));

	int minDivisor = 0;
	while(l <= r) {
		int divisor = l + (r-l) / 2;

		if(isBetweenThreshold(nums, divisor, threshold)) {
			minDivisor = divisor;
			r = divisor-1;
		} else {
			l = divisor+1;
		}
	}
	return minDivisor;
}
```

