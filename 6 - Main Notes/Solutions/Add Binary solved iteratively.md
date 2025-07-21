**Topic:** [[Bit Manipulation]] [[String]]
**Problem:**  [[Add Binary]]
**Last Modified:**  `2025-07-21 12:53`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: simple iterative solution. [[Logic Gates]] 

 
```cpp
string addBinary(string a, string b) {
	int i = a.length()-1, j = b.length()-1, carry = 0;
	string res = "";
	
	while(i >= 0 || j >= 0 || carry) {
		int d1 = 0, d2 = 0;
		
		if(i >= 0) d1 = a[i]-'0';
		if(j >= 0) d2 = b[j]-'0';

		int sum = d1 ^ d2 ^ carry;
		carry = (d1 & d2) || (d1 & carry) || (d2 & carry);

		res += sum + '0';
		i--, j--;
	}
	reverse(begin(res), end(res));
	return res;
}
```

