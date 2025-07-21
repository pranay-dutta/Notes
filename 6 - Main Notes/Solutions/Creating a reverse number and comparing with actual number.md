**Topic:** 
**Problem:**  [[Palindrome Number]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: Taking a **tempX** & **revX** using *temp* to get the *rev* of **x** if they are same means palindrome.

 
```cpp
bool isPalindrome(int x) {
	if (x < 0) return false;

	int tempX = x;
	long long revX = 0;

	while (tempX > 0) {
		int rem = tempX % 10;
		
		revX = (revX * 10) + rem;
		tempX /= 10;
	}
	return revX == x;
}
```

