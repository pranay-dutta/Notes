**Topic:** [[Recursion]]
**Problem:**  [[Find the K-th Character in String Game I]]
**Last Modified:**  `2025-07-03 15:14`

 $TC: O(k)$
 $SC: O(k)$

---
##### **Intuition**: simple do as said with iterative method

 
```cpp
char nextChar(char c) { 
	return (c-'a'+1)%26+'a';
} 

string appendWord(string word) {
	for (char& c: word) c = nextChar(c);
	return word;
}

char kthCharacter(int k) {
	string word = "a";
	while (word.size() < k) word += appendWord(word);
	return word[k - 1];
}

```

