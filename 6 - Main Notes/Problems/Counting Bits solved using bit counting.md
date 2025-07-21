**Topic:** [[Dynamic Programing]] [[Bit Manipulation]]
**Problem:**  [[Counting Bits]]
**Last Modified:**  `2025-07-22 02:12`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: count the bits and return it
 
```cpp
int popCount(int x) {
	int count = 0;
	for(int i = 0; i < 32; i++) {
		if((x >> i)&1) count++;
	}
	return count;
}
vector<int> countBits(int n) {
	vector<int> res(n+1);
	for(int i = 0; i < n+1; i++) {
		res[i] = popCount(i);
	}
	return res;
}
```

