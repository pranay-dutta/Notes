**Topic:** 
**Problem:**  [[Palindrome Number]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: Taking a **temp** & **rev** using *temp* to get the *rev* of **x** if they are same means palindrome.

 
```cpp
temp = x;
while(temp)
	rev = rev * 10 + (temp % 10); // rev * placevalue * lastdigit
	temp /= 10;
return rev == x;
```

