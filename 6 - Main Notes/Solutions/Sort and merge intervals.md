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
	
	for(i=0; n) {
		vec cur = iv[i]
		if(res.empty || cur[0] > res.back()[1]) res.push_back(cur);	
		else res.back()[1] = max(res.back()[1], cur[1]);
	  
	}

}


```

