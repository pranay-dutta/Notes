**Topic:**
**Problem:**  [[Valid Parentheses]]
**Last Modified:** `2025-05-11 20:39`

 $TC: O(n)$
 $SC: O(n)$

---
##### **Intuition**: simply *push* and *pop*parenthesis onto stack and check if it matches it's ***corresponding bracket***

 
```cpp
bool isValid(string s) {
	stack<int> st;
	if(s[i] == ')' && !st.empty() && st.top() == '(')
	//same 2 if conditon for curly brackets and square brackets
	else st.push(s[i]) //current element

	return st.empty(); // if it's not empty string of parethesis is not valid
}
```

