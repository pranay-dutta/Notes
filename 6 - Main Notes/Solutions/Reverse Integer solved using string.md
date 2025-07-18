**Topic:** [[Math]]
**Problem:**  [[Reverse Integer]]
**Last Modified:**  `2025-07-19 01:52`

 $TC: O(n)$
 $SC: O(d)$ *number of digits*

---
##### **Intuition**:  convert -X to positive and Reverse it with the help of string

 
```cpp
int reverse(int x) {
	bool neg = x < 0;

	long long absX = abs((long long)x); // use long long to handle INT_MIN safely
	string str = to_string(absX);

	std::reverse(str.begin(), str.end()); //O(n)

	long long newX = stol(str);
	if (newX > INT_MAX) return 0;

	return neg ? -newX : newX;
}
```

