**Topic:**  [[Segment Tree]] [[Design]]
*Last Modified**:  `2025-08-08 13:43`

---
`Problem:`
Given an integer array `nums`, handle multiple queries of the following types:

1. **Update** the value of an element in `nums`.
2. Calculate the **sum** of the elements of `nums` between indices `left` and `right` **inclusive** where `left <= right`.

Implement the `NumArray` class:

- `NumArray(int[] nums)` Initializes the object with the integer array `nums`.
- `void update(int index, int val)` **Updates** the value of `nums[index]` to be `val`.
- `int sumRange(int left, int right)` Returns the **sum** of the elements of `nums` between indices `left` and `right` 
	**inclusive** (i.e. `nums[left] + nums[left + 1] + ... + nums[right]`).

---

### Solutions -- 

###### 🟢 Best
 `Time O(n log(m)) Space O(4m)`  [[Range Sum Query - mutable solved using segment tree]]
----------------------------------------------------------------------------------------------
###### 🟡 Average
 `Time O() Space O()` 
----------------------------------------------------------------------------------------------
###### 🔴 Worst
 `Time O() Space O()`  *each range update will take* O(n) *if there is* **q** number of queries it would 
 take *O(q * n)* `!TLE`
----------------------------------------------------------------------------------------------

