**Topic:** [[Array]] [[Two Pointers]]
**Problem:**  [[3 Sum]]
**Last Modified:**  `2025-07-01 13:48`

 $TC: O(n^2)$
 $SC: O(1)$ excluding res  

---
##### **Intuition**: sort the array. fix a number n1 find complement(-n1) in remaining array
 
```cpp
vector<vector<int>> res;
void twoSum(vector<int>& nums, int target, int i, int j) {
	while(i < j) {
		int sum= nums[i] + nums[j];
		if(sum > target) j--;
		else if(sum < target) i++;
		else {
			while(i < j && nums[i]==nums[i+1]) i++; //skip duplicate n2
			while(i < j && nums[j]==nums[j-1]) j--; //skip duplicate n3
			
			res.push_back({-target, nums[i], nums[j]}); //found
			i++, j--;
		}

	}

}
	
vector<vector<int>> threeSum(vector<int>& nums) {
	sort(nums); //n log(n)
	for(i = 0; i<= n-3; i++) { //TC: O(n)
		if(i>0 && nums[i]==nums[i-1]) continue; //skip duplicate n1
		int complement = -nums[i]; 
		twoSum(nums, complement, i+1, n-1); //TC: ~(n) //serach for complement 
	}
	return res;
}

```

