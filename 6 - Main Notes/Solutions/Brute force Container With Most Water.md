**Topic:** [[Array]] [[Two Pointers]]
**Problem:**  [[Container With Most Water]]
**Last Modified:**  `2025-07-05 01:55`

 $TC: O(n^2)$
 $SC: O(1)$

---
##### **Intuition**: run two for loops to check every possible container.

 
```cpp
int maxArea(vector<int>& height) {
	int n = height.size();

	//i'th container water =  j-i * min(h[i], h[j]) 

	int maxWater = 0;
	for (int i = 0; i < n; i++) {
		int curWater = 0; 
		int source = height[i];

		for (int j = i+1; j < n; j++) {
			curWater = max(curWater, (j-i)*min(source, height[j]));
		}
		maxWater = max(maxWater, curWater);
	}
	return maxWater;
}
```

