**Topic:** [[Segment Tree]]
**Problem:**  [[Range Sum Query - Immutable]]
**Last Modified:**  `2025-08-08 01:44`

 $TC: O(n)$  *build (n)*  & *query(log (n))*
 $SC: O(4n)$

---
##### **Intuition**: Build segment tree and Do the range query
 
```cpp
class SegmentTree {
public:
    vector<int> segment;
    SegmentTree(int n) {
        segment = vector<int>(n);
    }
    void build(vector<int>& nums, int i, int l, int r) {
        if(l==r) {
            segment[i] = nums[l];
            return;
        }
        int mid = (l+r) / 2;
        int lc = 2*i+1, rc = 2*i+2;

        build(nums, lc,   l, mid);
        build(nums, rc, mid+1, r);

        //Backtrack and fill internal nodes
        segment[i] = segment[lc] + segment[rc];
    }

    int getQuery(int i, int l, int r, int qL, int qR) {
        //1. No overlap
        if(l > qR || r < qL) return 0;

        //2. Total overlap
        if(l >= qL && r <= qR) return segment[i];


        //3. Partial overlap
        int mid = (l+r) / 2;
        int lc = 2*i+1, rc = 2*i+2;

        int leftSum   = getQuery(lc,   l, mid, qL, qR); 
        int rightSum  = getQuery(rc, mid+1, r, qL, qR); 

        //return left and right subtree partial sum
        return leftSum + rightSum; 
    }

};
class NumArray {
private:
    SegmentTree seg;
    int n = 0;
public:
    NumArray(vector<int>& nums): seg(nums.size()*4) {
        n = nums.size();
        seg.build(nums, 0, 0, n-1);
    }
    
    int sumRange(int left, int right) {
        return seg.getQuery(0, 0, n-1, left, right);
    }
};
```

