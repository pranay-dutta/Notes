**Topic:** 
**Problem:**  [[Palindrome Number]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(d + n)$
 $SC: O(n)$

---
##### **Intuition**: Storing each **Digit** into a ***string or vector*** and comparing last index and first

 
```cpp
if(x < 0) return false;
while(x) {
	v.push_back(x % 10); //lastdigit
	x /=10; //reducing digit
}
for(i < v.size()) 
	if(v[i] != v[j]) 
		return false;
i++, j--;

return true;
```

