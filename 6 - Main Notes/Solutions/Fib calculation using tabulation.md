**Topic:** [[Tabulation]]
**Problem:**  [[Fibonacci Number]]
**Last Modified:**  `2025-05-13 19:35`

 $TC: O(n)$
 $SC: O(n)$

---
##### **Intuition**: use dp arr to *memoize* repeating results

 
```cpp
f[0]=0, f[1]=1
for(i=2; i<=n) {
	f[i]=f[i-1]+f[i-2];
}
return f[i]

```

