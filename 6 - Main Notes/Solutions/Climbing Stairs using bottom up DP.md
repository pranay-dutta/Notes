**Topic:** [[Dynamic Programing]]
**Problem:**  [[Climbing Stairs]]
**Last Modified:**  `2025-07-19 15:57`

 $TC: O(n)$
 $SC: O(n)$ 

---
##### **Intuition**: `dp[i]` is nothing but `fibonacchi series`

 
```cpp
int climbStairs(int n) {
	if(n == 1) return 1;

	int dp[n+1]; 
	dp[1] = 1; 
	dp[2] = 2; 

	for(int i = 3; i <= n; i++) {
		dp[i] = dp[i-1] + dp[i-2];
	}
	return dp[n];
}
```