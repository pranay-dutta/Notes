**Topic:** [[Two Pointers]]
**Problem:**  [[Find the Duplicate Number]]
**Last Modified:**  `2025-07-15 01:25`

 $TC: O(1)$
 $SC: O(n)$

---
##### **Intuition**: find cycle when the met at first. 
##### then reset the tortoise then move tortoise and hare slowly until they met second time. 

 
```cpp
f=n[0], s=n[0]

while(1)
s=n[s]  //move once
f=n[n[f]] //move twice
if(s==f) break //cycle found

//search for the duplicate by moving both slowly
while(s!=f) {
	s = n[s]
	f = n[f]
}
return s // or you can return f 
//their meeting spot is the starting of the cycle. ie. duplicate number
```

