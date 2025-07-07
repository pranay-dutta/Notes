**Topic:** [[Matrix]] [[Math]]
**Problem:**  [[Game of Life]]
**Last Modified:**  `2025-07-07 11:39`

 $TC: O(m*n * 8)$
 $SC: O(m*n)$

---
##### **Intuition**: Do as said, update the new state in a new array

```cpp
class Solution {
private: 
    int m, n;
    bool isValid(int i, int j) {
        return i >= 0 && i < m && j >= 0 && j < n;
    } 
    void handlePopulation(int i, int j, vector<vector<int>>& temp, int isLiveCell, int live) {
        if(isLiveCell) { //if live cell
            if(live < 2) temp[i][j] = 0; //under population
            else if(live >= 2 && live <= 3) temp[i][j] = 1; //next generation
            else temp[i][j] = 0; //under population

        } else { //if dead cell
            temp[i][j] = live == 3 ? 1 : 0;
        }
    }
public:

    vector<vector<int>> directions = {
        {0, 1},   {0, -1}, {-1, 0}, {1, 0},  // R L U D
        {-1, -1}, {-1, 1}, {1, -1}, {1, 1}}; // LD(U), RD(U), LD(B), RD(B)

    void gameOfLife(vector<vector<int>>& board) {
        // 1 = live 0 = dead

        // live < 2          -> dead
        // live >= 2 && <= 3 -> live
        // live > 3 &&       -> dead
        // dead == 3         -> live

        m = board.size();
        n = board[0].size();

        vector<vector<int>> temp(m, vector<int>(n, 0));

        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {

                int live=0;
                for(auto& dir: directions) {
                    int i_ = i + dir[0];
                    int j_ = j + dir[1];

                    if(isValid(i_, j_)) {
                        live += board[i_][j_];
                    }
                }

                handlePopulation(i, j, temp, board[i][j], live);
            }
        }
        board=temp;
    }
};


```