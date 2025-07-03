**Topic:** [[Array]] [[Matrix]]
**Problem:**  [[Spiral Matrix]]
**Last Modified:**  `2025-07-03 14:48`

 $TC: O(m*n)$
 $SC: O(1)$ *excluding result vector*

---
##### **Intuition**: iterate in spiral order and push the elements

```cpp
    vector<int> spiralOrder(vector<vector<int>> & matrix) {
        vector<int> res;
        int m = matrix.size(), n = matrix[0].size();

        int top = 0, bottom = m-1, left = 0, right = n-1;

        while(top <= bottom && left <= right) {
            //left to right
            for(int j = left; j <= right; j++)  res.pushb(matrix[top][j]);
            top++;
			
            //top to bottom
            for(int i = top; i <= bottom; i++) res.pushb(matrix[i][right]);
            right--;
			
            if(left > right || top > bottom) break;

            //right to left
            for(int j = right; j >= left; j--) res.pushb(matrix[bottom][j]);
            bottom--;
			
            //bottom to top
            for(int i = bottom; i >= top; i--) res.pushb(matrix[i][left]);
            left++;

        }
        return res;
    }
```
