**Topic:** [[Array]] [[Binary Search]]
**Problem:**  [[4 Sum]]
**Last Modified:**  `2025-07-16 01:19`
	
 $TC: O(n^3)$
 $SC: O(1)$

---
##### **Intuition**: sort and then do binary search

```cpp
// TC: (n^3)
// SC: O(1)
vector<vector<int>> result;
void twoSum(vector<int>& nums, int i, long long target, int a, int b) {
	int j = nums.size()-1;

	while(i < j) {
		int sum = nums[i] + nums[j];

		if(sum < target) i++;
		else if(sum > target) j--;
		else {
			result.push_back({nums[a], nums[b], nums[i], nums[j]});

			while(i < j && nums[i]==nums[i+1]) i++; // if duplicate c move on
			while(i < j && nums[j]==nums[j-1]) j--;  //if duplicate d move on
			i++, j--;
		}
	}
}
vector<vector<int>> fourSum(vector<int>& nums, int target) {
	int n = nums.size();

	sort(begin(nums), end(nums));

	for (int a = 0; a <= n - 4; a++) {
		if(a > 0 && nums[a]==nums[a-1]) continue; //if duplicate a move on
		
		for (int b = a+1; b <= n - 3; b++) {
			if(b > a + 1 && nums[b]==nums[b-1]) continue; //if duplicate b move on

			long long complement = (long long)target - (nums[a] + nums[b]);
			twoSum(nums, b+1, complement, a, b);
		}
	}
	return result;
}

```