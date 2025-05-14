**Topic:** 
**Problem:**  [[Count Number of Teams]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n3)$
 $SC: O(1)$

---
##### **Intuition**: forming all possible teams and checking **if** any of the **condition** met or not

 
```cpp
//r means rating
for(i = 0; i < n - 2; i++) {
	j = i + 1; //start from i + 1 element
	while(j < n - 1) {
		k = j + 1; //start from i + 2 or j + 1 element
		while(k < n) {
			if(r[i] < r[j] && r[j] < r[k]) || (r[i] > r[j] && r[j] > r[k])
			teamCount++;
		}
		k++;
	}
	j++;
}
```

