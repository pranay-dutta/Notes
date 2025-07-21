**Topic:** [[String]]
**Problem:**  [[Valid Palindrome]]
**Last Modified:**  `2025-07-22 02:57`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: 

```
Keep two pointers i and j
If they mismatch try skipping that character from either left or right side
And return the result
```

```cpp
bool validateSkip(string& s, int i, int j) {
	while (i < j) {
		if (s[i++] != s[j--]) return false;
	}
	return true;
}
bool validPalindrome(string s) {
	int i = 0, j = s.length() - 1;

	while (i < j) {
		if (s[i] != s[j]) {
			return validateSkip(s, i + 1, j) || validateSkip(s, i, j - 1);
		}
		i++, j--;
	}
	return true;
}
```

