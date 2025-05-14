**Topic:** [[Hash Table]]
**Problem:**  [[Majority Element]]
**Last Modified:**  `2025-05-13 01:43`

 $TC: O(n)$
 $SC: O(n)$

---
##### **Intuition**: store frequency and after that check the map

 
```cpp
for(x: n) mp[x]++
for([e, f]: mp) if f > (n.size()/2) return e //majority element always exist
```

