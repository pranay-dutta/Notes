**Topic:** [[Breadth-First Search]] [[Matrix]] 
**Problem:**  [[Max Area of Island]]
**Last Modified:**  `2025-07-21 11:33`

 $TC: O(m*n)$
 $SC: O(m*n)$

---
##### **Intuition**: keep a visited array if any cell is not visited do bfs. After who matrix is traversed you'll have Max Land Area

```cpp
int m, n;
vector<vector<int>> directions = {{0, 1}, {0, -1}, {1, 0}, {-1, 0}};
int BFS(vector<vector<int>>& grid, int i, int j, vector<vector<bool>>& visited) {
	queue<pair<int, int>> q; //{i, j}
	visited[i][j] = true;
	q.push({i, j});

	int landArea = 1;

	while(!q.empty()) { // m * n //if whole matrix is land
		auto [i, j] = q.front(); q.pop();

		for(auto& dir: directions) {
			int i_ = dir[0] + i;
			int j_ = dir[1] + j;
			
			if(i_ >= 0 && i_ < m && j_ >= 0 && j_ < n && !visited[i_][j_] && grid[i_][j_]) {
				landArea++;
				q.push({i_, j_});
				visited[i_][j_] = true;
			} 
		}
	}
	return landArea;
}
int maxAreaOfIsland(vector<vector<int>>& grid) {
	m = grid.size();
	n = grid[0].size();

	vector<vector<bool>> visited(m, vector<bool>(n, false)); //m * n
	int maxLandArea = 0;

	for(int i = 0; i < m; i++) { //m * n
		for(int j = 0; j < n; j++) {
			if(grid[i][j] && !visited[i][j]) {
				maxLandArea = max(maxLandArea, BFS(grid, i, j, visited));
			}
		}
	}
	return maxLandArea;
}
```

