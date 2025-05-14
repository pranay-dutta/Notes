**Topic:** [[Cumulative Sum]]
**Problem:**  [[Running Sum of 1d Array]]
**Last Modified:**  `2025-05-12 20:03`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: simply traverse and calculate 

 
```cpp
for(i=1<n) nums[i] += nums[i-1]
return nums
``

