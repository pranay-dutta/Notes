**Topic:** [[Include-Exclude]] [[Recursion]]
**Problem:**  [[Subsets]]
**Last Modified:**  `2025-07-22 03:13`

 $TC: O(2^n)$
 $SC:$ *total subsets* $O(2^n * n)$  *n is the number of elements*  , $O(n)$ *max depth of stack*

---
##### **Intuition**: Take or Not take at every index
 
```cpp
vector<vector<int>> res;
void solve(vector<int>& nums, int i, vector<int>& temp) {
	if(i >= nums.size()) {
		res.push_back(temp);
		return;
	}

	//Take 
	temp.push_back(nums[i]);
	solve(nums, i + 1, temp); //baki ka kudh dekh le

	temp.pop_back();
	solve(nums, i + 1, temp); //leap of faith
}
vector<vector<int>> subsets(vector<int>& nums) {
	vector<int> temp;
	solve(nums, 0, temp);
	return res;
}
```

