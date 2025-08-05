**Topic:**  [[Binary Search]] [[Binary Search on Answer]]
**Last Modified**:  `2025-08-05 02:44`

`Problem:`
You are given an integer `n` indicating there are `n` specialty retail stores. There are `m` product types of varying amounts,
which are given as a **0-indexed** integer array `quantities`, where `quantities[i]` represents the number of products of the `ith` product type.

You need to distribute **all products** to the retail stores following these rules:

- A store can only be given **at most one product type** but can be given **any** amount of it.
- After distribution, each store will have been given some number of products (possibly `0`). 
  Let `x` represent the maximum number of products given to any store. You want `x` to be as small as possible, i.e., 
  you want to **minimize** the **maximum** number of products that are given to any store.
Return _the minimum possible_ `x`.

==reduce the product given to each store such that all stores receives a type of product ==

### Solutions -- 

###### 🟢 Best
 `Time O(n log(n)) Space O(1)` [[Minimized Maximum of Products Distributed to Any Store solved using binary search]] 
----------------------------------------------------------------------------------------------
###### 🟡 Average
 `Time O() Space O()` 
----------------------------------------------------------------------------------------------
###### 🔴 Worst
 `Time O() Space O()` 
----------------------------------------------------------------------------------------------