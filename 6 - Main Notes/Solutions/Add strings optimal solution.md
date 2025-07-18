**Topic:** [[Math]] [[String]]
**Problem:**  [[Add Strings]]
**Last Modified:**  `2025-07-19 02:17`

`n = max(num1.length(), num2.length())`

 $TC: O(n)$
 $SC: O(1)$ *excluding result string*

---
##### **Intuition**: traverse from the right and add

 
```cpp
string addStrings(string num1, string num2) {
	int i = num1.size()-1, j = num2.size()-1;
	int carry = 0;

	string res = "";
	while (i >= 0 || j >= 0 || carry != 0) {
		int d1 = (i >= 0) ? num1[i--] - '0' : 0;
		int d2 = (j >= 0) ? num2[j--] - '0' : 0;
		int sum = d1 + d2 + carry;

		carry = sum / 10;
		char x = (sum % 10) + '0'; //+ '0' to convert into char
		res = x + res; 
	}
	return res;
}
```
