**Topic:** [[Dynamic Programing]]
**Problem:**  [[Best Time to Buy and Sell Stocks]]
**Last Modified:**  `2025-05-12 00:45`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**:  Assume purchase at day 0 traverse and **minimize purchase** and increase profit by searching **highest sell value**

 
```cpp
buyPrice = prices[0], curProfit = 0, maxProfit = 0 
for(0, n-1) {
	buyPrice = min(buyPrice, prices[i])
	curProfit = prices[i+1] - buyPrice
	maxProfit = max(maxProfit, curProfit)
}
return maxProfit
```

