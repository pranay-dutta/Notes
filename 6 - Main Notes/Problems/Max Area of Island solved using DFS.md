**Topic:** [[Depth-First Search]] [[Matrix]] 
**Problem:**  [[Max Area of Island]]
**Last Modified:**  `2025-07-21 11:33`

 $TC: O(m*n)$ *max depth of recursion stack*
 $SC: O(m*n)$

---
##### **Intuition**: keep a visited array if any cell is not visited do Dfs. After who matrix is traversed you'll have Max Land Area

```cpp
int m, n;
vector<vector<int>> directions = {{0, 1}, {0, -1}, {1, 0}, {-1, 0}};
int DFS(vector<vector<int>>& grid, int i, int j, vector<vector<bool>>& visited) {
	if(i < 0 || i >= m || j < 0 || j >= n || visited[i][j] || !grid[i][j]) return 0;

	visited[i][j] = true;
	int landArea = 1;

	for(auto& dir: directions) {
		int i_ = dir[0] + i;
		int j_ = dir[1] + j;
		landArea += DFS(grid, i_, j_, visited);
	}
	return landArea;
}
int maxAreaOfIsland(vector<vector<int>>& grid) {
	m = grid.size(), n = grid[0].size();

	vector<vector<bool>> visited(m, vector<bool>(n, false)); //m * n
	int maxLandArea = 0;

	for(int i = 0; i < m; i++) { //m * n
		for(int j = 0; j < n; j++) {
			if(grid[i][j] && !visited[i][j]) {
				maxLandArea = max(maxLandArea, DFS(grid, i, j, visited));
			}
		}
	}
	return maxLandArea;
}
```
