**Topic:** [[Math]]
**Problem:**  [[Plus One]]
**Last Modified:**  `2025-05-12 01:12`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**:  if **digits[i]** < 9 increment else make **digits[i]=0** , If all the way to start all *digits[i] is 9* then add 1 at the begin of **digits** arr

 
```cpp
//d is digits arr
for(n-1, 0) {
	if(d[i] < 9) ++d[i], return d;
	d[i]=0
}
d.insert(begin(d), 1); //add 1 if all digits were [9,9,9] -> [1, 0, 0, 0]
return d;

```
