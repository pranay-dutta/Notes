**Topic:** [[Two Pointers]] 
**Problem:**  [[Valid Palindrome]]
**Last Modified:**  `2025-07-04 00:39`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**:  compare using isalnum

 
```cpp
bool valid(char c) { //similar to isalnum
	int x = int(c);
	//          digit               alphabet
	return (x>=48 && x<=57) || (x>=97 && x<=122);
}

bool isPalindrome(string s) {
	int l=0, r=s.length()-1;

	while (l < r) {
		char a = tolower(s[l]);
		char b = tolower(s[r]);

		if(!isalnum(a)) l++;
		else if(!isalnum(b)) r--;
		else if(a!=b) return false; //base case
		else { l++, r--; } //shrink window 
	}
	return true;
}
```

