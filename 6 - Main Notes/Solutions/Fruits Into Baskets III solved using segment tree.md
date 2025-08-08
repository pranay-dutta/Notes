**Topic:** [[Segment Tree]]
**Problem:**  [[Fruits Into Baskets III]]
**Last Modified:**  `2025-08-08 14:20`

 $TC: O(n\log(m))$
 $SC: O(4m)$

---
##### **Intuition**: build Segment tree, keep Max sum range, Query and Update

 
```cpp
class SegmentTree {
public:
    vector<int> segment;
    SegmentTree(int size)  {
        segment = vector<int>(size);
    } 

    void build(vector<int>& nums, int i, int l, int r) { //log(m)
        if(l == r) {
            segment[i] = nums[l]; //l or r does not matter.
            return;
        }

        int m = (l + r) / 2;

        build(nums, 2*i+1, l, m);   //left child is at 2*i+1
        build(nums, 2*i+2, m+1, r); //right child is at 2*i+2

        //backtrack fill the internal nodes [max, prod, sum. etc]
        segment[i] = max(segment[2*i+1], segment[2*i+2]);
    }

    bool query(int i, int l, int r, int queryKey) {
        if(queryKey > segment[i]) return false; //base case. can't put in the root basket 

        if(l == r) { //if found
            segment[i] = -1;
            return true;
        }

        bool placed = false;
        int m = (l +r ) / 2;

        if(segment[2*i+1] >= queryKey) { //left child
            placed = query(2*i+1, l, m, queryKey);
        } else {                               //right child
            placed = query(2*i+2, m+1, r, queryKey);
        }

        segment[i] = max(segment[2*i+1], segment[2*i+2]);
        return placed;
    }
};
class Solution {
public:
    int numOfUnplacedFruits(vector<int>& fruits, vector<int>& baskets) {
        int n = baskets.size();
        SegmentTree seg(n*4); //many need to query left node childs. That's why dummy nodes

        seg.build(baskets, 0, 0, n-1); //log(m)

        int placedFruits = 0;
        for(int x: fruits) { // n 
            if(seg.query(0, 0, n-1, x)) { //log(m)
                placedFruits++;
            }
        }
        return n - placedFruits;
    }
};
```

