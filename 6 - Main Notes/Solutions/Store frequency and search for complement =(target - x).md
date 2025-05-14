**Topic:** [[Hash Table]]
**Problem:** [[Two Sum]]
**Last Modified**:  `2024-07-31 00:02

 $TC: O(2n)$
 $SC: O(n)$
 
---
##### **Intuition**:  find the **target - nums[i]** index inside *map*
 

```cpp
for (i = 0; i < n) mp[nums[i]] = i; // storing index

for (i = 0; i < n) {
	complement = target - nums[i]; // complement value
	if(mp[complement] != 0 && mp[complement] != i)  return {i, mp[complement]};
    
}
```
