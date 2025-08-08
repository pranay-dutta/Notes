**Topic:**  [[Segment Tree]] [[Binary Search]]
**Last Modified**:  `2025-08-08 13:46`

---
`Problem:`

You are given two arrays of integers, `fruits` and `baskets`, each of length `n`, where `fruits[i]` 
represents the **quantity** of the `ith` type of fruit, and `baskets[j]` represents the **capacity** of the `jth` basket.

From left to right, place the fruits according to these rules:

- Each fruit type must be placed in the **leftmost available basket** with a capacity **greater than or equal** to the quantity of that fruit type.
- Each basket can hold **only one** type of fruit.
- If a fruit type **cannot be placed** in any basket, it remains **unplaced**.

Return the number of fruit types that remain unplaced after all possible allocations are made.

---
### Solutions -- 

###### 🟢 Best
 `Time O(n logn(m)) Space O()` 
----------------------------------------------------------------------------------------------
###### 🟡 Average
 `Time O() Space O()` 
----------------------------------------------------------------------------------------------
###### 🔴 Worst
 `Time O(n*m) Space O(1)` [[Fruits Into Baskets II solved using brute force]] 
----------------------------------------------------------------------------------------------