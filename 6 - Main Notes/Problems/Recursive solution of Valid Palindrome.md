**Topic:** [[Recursion]]
**Problem:**  [[Valid Palindrome]]
**Last Modified:**  `2025-07-04 00:46`

 $TC: O(n)$
 $SC: O(n)$ *stack space* 

---
##### **Intuition**: shrink from both side if the are both alpha or numeric, compare them and 
 
```cpp
bool f(string& s, int l, int r) {
	if(l>=r) return true; //base case
	
	char a=tolower(s[l]), b=tolower(s[r]);

	if(!isalnum(a)) return f(s, l+1, r); //increase left pointer
	else if(!isalnum(b)) return f(s, l, r-1); //decrease right pointer
	else if (a!=b) return false; //if not palindrome
	return f(s,l+1, r-1); //default return
}
bool isPalindrome(string s) {
	return f(s, 0, s.length()-1);
}

```

