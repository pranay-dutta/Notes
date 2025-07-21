**Topic:** [[Bit Manipulation]] [[String]]
**Problem:**  [[Add Binary]]
**Last Modified:**  `2025-07-21 12:53`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: simple iterative solution. [[Logic Gates]] 
 
```cpp
string addBinary(string a, string b) {
	int i = a.length() - 1, j = b.length() - 1, carry = 0;

	string ans = "";
	while (i >= 0 || j >= 0 || carry) {
		int sum = carry;

		if (i >= 0) sum += a[i--] - '0';
		if (j >= 0) sum += b[j--] - '0';

		ans += (sum % 2) + '0'; 
		carry = sum / 2;                 
	}
	reverse(begin(ans), end(ans));

	return ans;
}
```
