**Topic:** [[Greedy]]
**Problem:**  [[Best Time to Buy and Sell Stock II]]
**Last Modified:**  `2025-05-12 19:08`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: buy today and sell next day to get the **max profit**

 
```cpp
//p = prices arr
//p[i+1] is next day 
//p[i]   is current day
for(i=0, n-1) {
	if(p[i+1]>p[i]) profit += p[i+1]-p[i] 
}
return profit

```
