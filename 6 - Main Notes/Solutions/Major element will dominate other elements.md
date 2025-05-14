**Topic:** [[Boyer Moore Voting Algorithm]]
**Problem:**  [[Majority Element]]
**Last Modified:**  `2025-05-12 22:42`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: major element will always **dominate other half** of the array

 
```cpp
e = f = 0
for(x: n) {
	if(f==0) e=x //assign new element
	
	if(e==x) f++ //same element found increase freq
	else f--; //else reduce freq
}
return e;

```

