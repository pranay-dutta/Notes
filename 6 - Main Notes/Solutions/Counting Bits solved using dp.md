**Topic:** [[Dynamic Programing]] 
**Problem:**  [[Counting Bits]]
**Last Modified:**  `2025-07-22 02:32`

#editpending #addhandwrittennote #addnoteofrecursiontree

 $TC: O(n)$
 $SC: O(1)$ *auxiliary space*

---
##### **Intuition**: calculate bit count from n/2 the element

 
```cpp
// TC: O(n)
// SC: O(1) auxilary space

vector<int> countBits(int n) {
	vector<int> dp(n + 1, 0);
	if (n == 0) return dp;

	dp[1] = 1;

	for (int i = 2; i <= n; i++) {
		dp[i] = (i & 1) + dp[i / 2];
	}
	return dp;
}
```

