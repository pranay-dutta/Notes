**Topic:** 
**Problem:**  [[Total Characters in String After Transformations I]]
**Last Modified:**  `2025-05-14 01:08`

 $TC: O(n + (t*26))$
 $SC: O(1)$

---
##### **Intuition**: take a temporary **mp** and count next char **frequency**. Repeat the process **t** times

 
```cpp
//s is string
M=1e9+7
mp(26,0) 
for(c: s) mp[c]++

while(t--) {
	t(26, 0) //temporary map, created using vector<int>
	for(i=0<26) {
		char e=i+'a' //i=0+'a' --> 'a', i=1+'a'--> 'b' ... 
		int f=mp[i] //frequency

		if(e=='z') 
			t[0] = (t[0] + f) % M //'a'
			t[1] = (t[1] + f % M) //'b'
		else 
			t[i+1] = (t[i+1] + f) % M  //next char in temp
	}
	//# Important function. Erases the old map and moves. Does not copy
	mp=move(t)
}

res=0
for(i=0<26) res = (res + mp[i]) % M
return res;

```

