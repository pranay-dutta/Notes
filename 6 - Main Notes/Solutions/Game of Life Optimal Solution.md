**Topic:** [[Matrix]] [[Math]]
**Problem:**  [[Game of Life]]
**Last Modified:**  `2025-07-07 12:22`

<img src="game-of-life-optimal.png" width=500 style="border-radius: 10px" />


 $TC: O(2 (m*n))$
 $SC: O(1)$

---
##### **Intuition**:
- Mark **dead** as -1
- **resurrected** as 2
- **count Live every direction** if i, j  **abs(i+dir0, j+dir1) == 1** //this will give alive cells 😉

```cpp
public:
    vector<vector<int>> directions = {{0, 1}, {0, -1}, {-1, 0}, {1, 0}, {1, 1}, {-1, 1}, {-1, -1}, {1, -1}}; //R L D U (RD B), (LD B), (LD U), (RD U)
    void gameOfLife(vector<vector<int>>& board) {
        const int m = board.size();
        const int n = board[0].size();

        auto countLive = [&](int i, int j) {
            int cnt = 0;
            for(auto& dir: directions) {
                int i_ = i + dir[0];
                int j_ = j + dir[1];

                if(i_ >= 0 && i_ < m && j_ >= 0 && j_ < n && abs(board[i_][j_]) == 1) {
                    ++cnt;
                }
            }
            return cnt;
        };

        // First pass: mark transitions in‑place
        for (int i = 0; i < m; ++i) {
            for (int j = 0; j < n; ++j) {
                int live = countLive(i, j);
                if (board[i][j] == 1 && (live < 2 || live > 3)) board[i][j] = -1; // live → dead
                else if (board[i][j] == 0 && live == 3) board[i][j] = 2; // dead → live
            }
        }

        // Second pass: finalize states
        for (int i = 0; i < m; ++i) {
            for (int j = 0; j < n; ++j)
                board[i][j] = board[i][j] > 0 ? 1 : 0;
        }
    }
```

