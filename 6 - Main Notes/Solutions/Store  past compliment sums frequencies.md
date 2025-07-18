**Topic:** [[Cumulative Sum]]
**Problem:**  [[Subarray Sum Equals K]]
**Last Modified:**  `2025-07-03 02:20`

 $TC: O(n)$
 $SC: O(n)$

---
##### **Intuition**: store count of past sums, count total and fine the frequency of "compliment || sub sum"

 
```cpp
int subarraySum(vector<int>& nums, int k) {
	unordered_map<int,int> mp;

	int t = 0 c = 0 n = nums.size();
	mp[0] = 1; //for no sub sum

	for (int& x: nums) {
		t += x;

		//[1,   2,   3,    4,    2,    3]  k = 4
		// 1    3    6    10    12     15 
		//               10-4=6 yes seen only once

		if(mp[t-k]) c += mp[t-k];
		
		++mp[t];
	}
	return c;
}
```

