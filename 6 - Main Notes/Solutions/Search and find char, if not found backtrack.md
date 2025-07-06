**Topic:** [[Backtracking]] [[Matrix]]
**Problem:**  [[Word Search]]
**Last Modified:**  `2025-07-07 01:58`

 $TC: O(m * n * (4^L))$ `L = word.length`
 $SC: O(L)$

---
##### **Intuition**: find pivot aka starting char, start recursion if found return else backtrack and revert cells

```cpp
int m, n;
vector<vector<int>> directions = {{0, 1}, {0, -1}, {1, 0}, {-1, 0}};

bool found(int i, int j, int index, vector<vector<char>>& board, string& word) {
	if(index == word.length()) return true; //all char exhausted 

	if(i<0 || i>= m || j<0 || j>=n || board[i][j]=='$') return false; //board[i][j]=='$' means visited
	if(board[i][j] != word[index]) return false; //if not same character

	char temp = board[i][j]; //store in temp
	board[i][j] = '$';

	for(auto& dir: directions) {
		int i_ = i + dir[0];
		int j_ = j + dir[1];

		if(found(i_, j_, index+1, board, word)) return true;
	}

	//backtrack
	board[i][j] = temp; //revert
	return false;
}

bool exist(vector<vector<char>>& board, string word) {
	m = board.size();
	n = board[0].size();

	for(int i = 0; i <m; i++) {
		for(int j = 0; j <n; j++) {
			if(board[i][j]==word[0]) { //pivot char found; ie. starting char
				if(found(i, j, 0, board, word)) return true;
			}
		}
	}
	return false;
}
```

