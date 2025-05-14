**Topic:** 
**Problem:**  [[Move Zeros]]
**Last Modified:**  `2025-05-12 15:24`

 $TC: O(n)$
 $SC: O(n)$

---
##### **Intuition**: copy the **non-zero** values then put them  in nums, after that put **zeros**

 
```cpp
vector<int> e
for(x: nums) if(x) e.push_back(e)
for(i<n) nums[i] = i < e.size() ? e[i] : 0
```
