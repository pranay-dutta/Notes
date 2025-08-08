**Topic:** [[Segment Tree]]
**Problem:**  [[Fruits Into Baskets II]]
**Last Modified:**  `2025-08-08 14:12`

 $TC: O(n\ log(m))$
 $SC: O(4m)$

---
##### **Intuition**: store the range sums and query to get optimal place to place a fruit

 
```cpp
class SegmentTree {
public: 
    vector<int> segment;
    SegmentTree(int n) {
        segment = vector<int>(n);
    }

    void build(vector<int>& nums, int i, int l, int r) {
        if(l == r) {
            segment[i] = nums[r]; //l or r does not matter because here we only have one element. and l & r both pointing that
            return;
        }

        int m = (l+r) / 2;
        int lc = 2*i+1, rc = 2*i+2; //left child and right child

        build(nums, lc, l,   m);
        build(nums, rc, m+1, r);

        //Backtrack and fill the internal nodes. [prod, max, min, avg. etc]
        segment[i] = max(segment[lc], segment[rc]);
    }
    bool query(int i, int l, int r, int queryKey) {
        if(queryKey > segment[i]) return false; //can't put on root basket. Or recursion root basket

        if(l==r) { //reached to one left means can put current fruit. 
            segment[i] = -1; //mark the basket full with -1
            return true;
        }

        int m = (l+r) / 2;
        int placed = false;
        int lc = 2*i+1, rc = 2*i+2; //left child and right child

        if(segment[lc] >= queryKey) {
            placed = query(lc,  l, m, queryKey);
        } else {
            placed = query(rc, m+1, r, queryKey);
        }

        segment[i] = max(segment[lc], segment[rc]);
        return placed;
    }

};
class Solution {
public:
    int numOfUnplacedFruits(vector<int>& fruits, vector<int>& baskets) {
        int n = baskets.size();
        SegmentTree seg(n*4); //n*4 because may have to query child's child.

        seg.build(baskets, 0, 0, n-1);

        int placed = 0;
        for(int x: fruits) {
            if(seg.query(0, 0, n-1, x)) placed++;
        }
        return n - placed;
    }
};
```

