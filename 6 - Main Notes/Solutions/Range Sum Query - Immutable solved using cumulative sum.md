**Topic:** [[Cumulative Sum]]
**Problem:**  [[Range Sum Query - Immutable]]
**Last Modified:**  `2025-08-08 01:02`

 $TC: O(n)$
 $SC: O(n)$

![[cumulative-range-sum-query.png]]

---
##### **Intuition**: build the **Cumulative sum** array if *L ... R* range is been asked return `Sum[R] - Sum[L-1]`

```cpp
class NumArray {
public:
    vector<int> v;
    NumArray(vector<int>& nums) {
        int n = nums.size();
        v.resize(n);

        for(int i = 0; i < n; i++) {
            v[i] = (i > 0) ? nums[i] + v[i-1] : nums[i];
        }
    }
    
    int sumRange(int left, int right) {
        return left > 0 ? v[right] - v[left-1] : v[right];
    }
};
```

