**Topic:** [[Cumulative Sum]]
**Problem:**  [[Find Pivot Index]]
**Last Modified:**  `2025-05-12 20:35`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: calculate **total sum** then calculate **left sum** and compare

 
```cpp
//n = nums
sumR = accumulate(nums)
sumL = 0
for(i=0<n) {
	sumR -= n[i]
	if(sumR==sumL) return i
	sumL += n[i]
}
return -1 //if no pivot index found

```

