**Topic:** [[Dynamic Programing]] [[Bit Manipulation]]
**Problem:**  [[Counting Bits]]
**Last Modified:**  `2025-07-22 02:15`

 $TC: O(n)$
$SC$ : *Total: $O(n)$        `for res[] and memo table t[]`*
*Aux stack: $O(log n)$  `for recursion depth`*

---
##### **Intuition**: each time divide by half but memoize it
 
```cpp
// TC: O(n)
// SC: total(n) (res vector)
//     O(log n) worst-case (for first call to bitCount(n))
//     O(1) average-case per call (after memoization fills)

int t[100001];
int bitCount(int n) {
	if(n == 0) return 0;
	if(n == 1) return 1;

	if(t[n] != -1) return t[n];

	return t[n] = (n&1) + bitCount(n/2);
}
vector<int> countBits(int n) {
	vector<int> res(n+1, 0);
	memset(t, -1, sizeof(t));
	
	for(int i=0; i <= n; i++) {
		res[i] = bitCount(i);
	}
	return res;
}
```
