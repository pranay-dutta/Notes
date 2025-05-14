**Topic:** 
**Problem:**  [[Fibonacci Number]]
**Last Modified:**  `2025-05-13 19:31`

 $TC: O(2^n)$
 $SC: O(n: sys-stack)$

---
##### **Intuition**: calculate using recursion

 
```cpp
n==0 return 0
n==1 return 1;
return f(n-1) + f(n-2)
```

