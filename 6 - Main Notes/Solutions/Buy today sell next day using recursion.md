**Topic:** [[Greedy]]
**Problem:**  [[Best Time to Buy and Sell Stock II]]
**Last Modified:**  `2025-05-12 19:23`

 $TC: O(n)$
 $SC: O(n) .. system-stack$

---
##### **Intuition**: 

 
```cpp
//p is prices arr
int helper(i,profit,p) {
	if i>=n return profit
	if p[i]>p[i-1] profit += p[i]-p[i-1]
	return helper(i+1, profit, p) //call for next day
}
int maxProfit(prices) {
	return helper(1, 0, prices)
}

// Another way
int maxProfit(p, profit=0, i=1) { //default parameter value
	if i>=n return profit
	if p[i]>p[i-1] profit += p[i]-p[i-1]
	return getProfit(p, profit, i+1)
}
```