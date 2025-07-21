**Topic:**  [[Dynamic Programing]] [[Bit Manipulation]]
**Last Modified**:  `2025-07-22 02:09`

`Problem: `
```
Input: n = 5
Output: [0,1,1,2,1,2]

Explanation:
0 --> 0       => 0
1 --> 1       => 1
2 --> 10      => 1
3 --> 11      => 2
4 --> 100     => 1
5 --> 101     => 2
```

### Solutions -- 

###### 🟢 Best
 `Time O(n) Space O(1): auxilary space`  [[Counting Bits solved using bit counting]]
 `Time O(n) Space O(n: dp-array)`  [[Counting Bits solved using dp]]
----------------------------------------------------------------------------------------------
###### 🟡 Average
 `Time O(n) Space O(n)`  [[Counting Bits solved using recursion + memo]]
----------------------------------------------------------------------------------------------
###### 🔴 Worst
 `Time O(n log n) Space O(n)`  [[Counting Bits solved using recursion]]
----------------------------------------------------------------------------------------------

