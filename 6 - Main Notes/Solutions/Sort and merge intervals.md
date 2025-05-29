**Topic:** [[Array]]
**Problem:**  [[Merge Intervals]]
**Last Modified:**  `2025-05-28 01:28`

 $TC: O(n$ $log(n))$
 $SC: O(1)$ *excluding result array*

---
##### **Intuition**: sort the array, compare with the last element of res
 
```cpp
//iv=intervals array
example iv= [[1,3],[2,6],[8,10],[15,18]]
merge(vec<vec<int>>& iv) {
	sort(iv)
	vec r //result
	
	for(i=0; n) {
		vec cur = iv[i]
		if(r.empty || cur[0] > r.back()[1]) r.push_back(cur);	
		else r.back()[1] = max(r.back()[1], cur[1]); //compare with the last element
	}
}
```

