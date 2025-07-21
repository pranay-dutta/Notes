**Topic:** [[Dynamic Programing]] [[Bit Manipulation]]
**Problem:**  [[Counting Bits]]
**Last Modified:**  `2025-07-22 02:15`

 $TC: O(n \log n)$
$SC: O(n)$ *total (res vector)*, *or $O(\log n)$ auxiliary (recursion stack)*

---
##### **Intuition**: each time divide by half
 
```cpp
// TC: O(n log n)
// SC: O(n) total (res), or O(log n) auxiliary (recursion stack)
int bitCount(int n) {
	if(n == 0) return 0;
	if(n == 1) return 1;

	return (n&1) + bitCount(n/2);
}
vector<int> countBits(int n) {
	vector<int> res(n+1, 0);
	for(int i=0; i <= n; i++) {
		res[i] = bitCount(i);
	}
	return res;
}
```
