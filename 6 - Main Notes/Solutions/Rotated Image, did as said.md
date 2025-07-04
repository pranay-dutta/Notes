**Topic:** [[Matrix]]
**Problem:**  [[Rotate Image]]
**Last Modified:**  `2025-07-05 02:10`

 $TC: O(m*n)$
 $SC: O(m*n)$

---
##### **Intuition**: Build temp row => bottom of the first col to the top, => then push the temp => then move to the next column

 
```cpp
//TC: O(n^2)
//SC: O(n^2)
void rotate(vector<vector<int>>& matrix) {
	int i = n-1, j = 0;

	vector<vector<int>> res;
	for(int j = 0; j < n; j++) {
		vector<int> temp;
		for(int i = n-1; i >=0; i--) {
			temp.push_back(matrix[i][j]);
		}
		res.push_back(temp);
	}
	matrix = res;
}
```

