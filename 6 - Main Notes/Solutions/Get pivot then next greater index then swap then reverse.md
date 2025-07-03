**Topic:** [[Two Pointers]]
**Problem:**  [[Next Permutation]]
**Last Modified:**  `2025-07-03 12:09`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: as said in the tittle: get pivot > get next greater element index > swap the elements > reverse

 
```cpp
void nextPermutation(vector<int>& nums) {
	int n=nums.size(), pivot = n-2;

	// 1) find right‑most “pivot” that is smaller than its next element
	while(pivot >= 0 && (nums[pivot] >= nums[pivot+1])) --pivot; 

	if(pivot >= 0) {
		// 2) find the smallest element > nums[pivot] to its right (scan from end)
		int j = n - 1;
		while (nums[j] <= nums[pivot]) --j;
		swap(nums[pivot], nums[j]);
	}

	// 3) reverse the suffix to get the minimal order
	reverse(begin(nums)+pivot+1, end(nums));
}
```

