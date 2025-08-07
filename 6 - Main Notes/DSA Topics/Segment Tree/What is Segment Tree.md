📌 **Segment Tree** is an efficient data structure that allows

- **Efficient querying** of *intervals\range*😲
- **Efficient Updating** of *intervals\range*😳

> **Examples:** range queries to find
- Sum
- Minimum
- Maximum
- Product etc.

---
## Important Observations

1. Binary Tree 
2. **2** children of all non-left nodes. 
3. **Left Nodes** - Represents a single element in an array
4. **Root Node** - Represents entire array
5. **Other Nodes** - Represents array segments
6. **Height** - $⌈log\ (N)⌉$ - **N** is the size of the array
7. **Height difference of left & right subtree** <= 1 *i.e.  [[Balanced Binary Tree]]*

---
 *Number of nodes in segment tree*
- $N + N/2\ + N/4 \  + \ . . . . 1$   **=>  2 * N** ===> *[[Geometric Progression]]*
- If ***N*** is odd then number of nodes is => ***2 * N - 1***

- **Leaf** = N 
- **Internal** = N-1 
So, *N + N-1* => **(2N - 1)** => ≈ **2N**
---