**Topic:** [[Segment Tree]] [[Design]]
**Problem:**  [[Range Sum Query - mutable]]
**Last Modified:**  `2025-08-08 21:42`

 $TC: O(n\ log(m))$
 $SC: O(4m)$

---
##### **Intuition**: Create segment Tree, update Query, and Get Query

 
```cpp
class SegmentTree {
public:
    vector<int> segment;
    SegmentTree(int size) {
       segment = vector<int>(size);
    }
    void build(vector<int>& nums, int i, int l, int r) {
        if(l==r) {
            segment[i] = nums[l];
            return;
        }

        int mid = (l+r) / 2;
        int lc = 2*i+1, rc = 2*i+2;

        build(nums, lc, l,   mid);
        build(nums, rc, mid+1, r);

        segment[i] = segment[lc] + segment[rc];
    }

    int getQuery(int i, int l, int r, int qL, int qR) {
        //1. No Overlap
        if(l > qR || r < qL) return 0;

        //2. Total Overlap
        if(l >= qL && r <= qR) return segment[i];

        //3. Partial Overlap
        int mid = (l+r) / 2;
        int lc = 2*i+1, rc = 2*i+2;

        int leftSum = getQuery(lc, l, mid,  qL, qR);  //left subtree
        int rightSum = getQuery(rc, mid+1, r, qL, qR); //right subtree
        
        return leftSum + rightSum;
    }

    void updateQuery(int i, int l, int r, int index, int val) {
        if(l==r) {
            segment[i] = val;
            return;
        }

        int mid = (l+r) / 2;
        int lc = 2*i+1, rc = 2*i+2;

        if(index <= mid) {
            updateQuery(lc, l, mid , index, val);
        } else {
            updateQuery(rc, mid+1, r, index, val);
        }

        segment[i] = segment[lc] + segment[rc];
    }
};
class NumArray {
public:
    SegmentTree *seg;
    int n = 0;
    NumArray(vector<int>& nums) {
        n = nums.size();
        seg = new SegmentTree(n*4);
        seg->build(nums, 0, 0, n-1);
    }
    
    void update(int index, int val) {
        seg->updateQuery(0, 0, n-1, index, val);
    }
    
    int sumRange(int left, int right) {
        return seg->getQuery(0, 0, n-1, left, right);
    }
};
```

