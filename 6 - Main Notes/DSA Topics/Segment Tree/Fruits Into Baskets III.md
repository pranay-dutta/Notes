**Topic:**  [[Segment Tree]]
**Last Modified**:  `2025-08-08 14:17`

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
 `Time O(n log(m)) Space O(4m)` [[Fruits Into Baskets III solved using segment tree]]
----------------------------------------------------------------------------------------------
###### 🟡 Average
 `Time O() Space O()` 
----------------------------------------------------------------------------------------------
###### 🔴 Worst
 `Time O() Space O()` *brute force won't get accepeted since constraint is so high*
----------------------------------------------------------------------------------------------

