**Topic:** [[Dynamic Programing]]
**Problem:**  [[Climbing Stairs]]
**Last Modified:**  `2025-07-19 15:57`

 $TC: O(n)$
 $SC: O(n)$ *max depth of stack at any time*

---
##### **Intuition**: take 1 or take 2 step + memoize it

 
```cpp
int t[45];
int solve(int n, int currentStair) {
	if(currentStair == n) return 1;
	if(currentStair > n) return 0;

	if(t[currentStair] != -1) return t[currentStair];

	//Two possibilities step1 or step2
	int stepOne = solve(n, currentStair + 1); 
	int stepTwo = solve(n, currentStair + 2);

	return t[currentStair] = stepOne + stepTwo;
}
int climbStairs(int n) {
	memset(t, -1, sizeof(t))
	return solve(n, 0);
}
```
