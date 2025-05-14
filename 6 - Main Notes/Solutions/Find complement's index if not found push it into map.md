**Topic:** [[Hash Table]]
**Problem:** [[Two Sum]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n)$
 $SC: O(n)$

---
##### **Intuition**:  find the **complement's index** index inside *map* 

 
```cpp
for (i = 0; i < n) {
	complement = target - nums[i]; // complement value
	if(mp[complement] != 0 && mp[complement] != i)  return {i, mp[complement]};
    mp[nums[i]] = i //storing idex
}
```
```
