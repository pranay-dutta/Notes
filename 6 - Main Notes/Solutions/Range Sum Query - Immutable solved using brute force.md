**Topic:** [[Brute Force]]
**Problem:**  [[Range Sum Query - Immutable]]
**Last Modified:**  `2025-08-08 00:59`

 $TC: O(q * n)$  *q is the number of queries* and *n is the length of the nums*
 $SC: O(n)$

---
##### **Intuition**: simply do the brute force 

 
```cpp
class NumArray {
private:
    vector<int> nums;

public:
    NumArray(vector<int>& nums) { this->nums = nums; };

    int sumRange(int left, int right) {
        int sum = 0;
        while(left <= right) {
            sum += nums[left];
            left++;
        }
        return sum;
    }
};
```

