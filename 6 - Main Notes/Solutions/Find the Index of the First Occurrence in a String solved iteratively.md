**Topic:** [[String]]
**Problem:**  [[Find the Index of the First Occurrence in a String]]
**Last Modified:**  `2025-07-22 02:43`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: simple iterative solution
 
```cpp
int strStr(string haystack, string needle) {
	for(int i = 0; i < haystack.size(); i++) {
		int k = i, j = 0;
		while(k < haystack.size() && j < needle.size() && haystack[k] == needle[j]) {
			j++, k++;
		}
		if(j==needle.size()) return i; //if j reaches needle.size => needle is been found
	}
	return -1;
}
```

