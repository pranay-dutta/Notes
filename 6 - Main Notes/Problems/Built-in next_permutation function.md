**Topic:** [[Two Pointers]]
**Problem:**  [[Next Permutation]]
**Last Modified:**  `2025-07-03 11:56`

 $TC: O(n)$
 $SC: O(n)$

---
##### **Intuition**: use built-in function

 
```cpp
void nextPermutation(vector<int>& nums) {
	next_permutation(nums.begin(), nums.end()); //O(n)
	return;
}
```

