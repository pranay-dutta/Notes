**Topic:** [[Two Pointers]] [[Array]]
**Problem:**  [[Container With Most Water]]
**Last Modified:**  `2025-07-05 01:58`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: choose the lower boundary to calculate water amount. Move the lower boundary, or move the right boundary (J) to get other containers

 
```cpp
int maxArea(vector<int>& height) {
	int n = height.size(), i=0, j=n-1;

	int maxWater = 0;

	while(i<j) {
		int minBoundary = min(height[i], height[j]);
		int containerWidth = j-i;
		maxWater = max(maxWater, containerWidth*minBoundary);

		if(height[i]<height[j])i++;
		else j--;
	}
	return maxWater;
}
```

