**Topic:** 
**Problem:**  [[Move Zeros]]
**Last Modified:**  `2025-05-12 15:20`

 $TC: O(2n)$
 $SC: O(1)$

---
##### **Intuition**: shift values to the **left** overriding zeros

 
```cpp
insIdx = 0
//shift values to the left
for(x: nums) if(x) nums[insIdx++] = x

//add zeros after that
for(insIdx < n) nums[insIdx++] = 0

```
