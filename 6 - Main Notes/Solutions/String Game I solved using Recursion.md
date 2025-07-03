**Topic:** [[Recursion]]
**Problem:**  [[Find the K-th Character in String Game I]]
**Last Modified:**  `2025-07-03 15:09`

 $TC: O(k)$
 $SC: O(k)$

---
##### **Intuition**: store dummy=word modify dummy and add to word ♾️

 
```cpp
    string solve(string w, int k) {
        if(w.size >= k) return w; //base case

        string dummy = w;
        for(char& c: dummy) c = c=='z' ? 'a' : c+1;

        return solve(w + dummy, k); 
    }
	
    char kthCharacter(int k) {
        string word = "a"; //Alice starts with 'a'
		
        string res = solve(word, k);

        return res[k-1];
    }

```

