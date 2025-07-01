**Topic:** [[Array]] [[Cumulative Sum]]
**Problem:**  [[Product of Array Except Self]]
**Last Modified:**  `2025-07-01 15:16`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: calculate the product, keep a frequency of zeros, if zero occurs more than one time cumulative-product is 0, keeping that in mind divide the prod with nums[i]

 
```cpp
vector<int> productExceptSelf(vector<int>& nums) {
	long long prod = 1 
	int n = nums.size(), zeroFreq = 0;

	for(x: nums) 
		x ? prod *= x : zeroFreq ++;

	for (int i = 0; i < nums.size(); i++) {
		int x = nums[i];
		
		if(zeroFreq == 1 && nums[i] == 0) nums[i]=prod; //if only one '0' and current element is '0'
		else if(zeroFreq >= 1) nums[i]=0; //if 2 or more zeros; then the cumulative product is '0'
		else nums[i] = prod/x; //else exclude the cur element
	}
	return nums;
}
```

