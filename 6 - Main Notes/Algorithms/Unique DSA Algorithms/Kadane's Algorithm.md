## 🎯 Goal

Find the **maximum sum of a contiguous subarray** in `O(n)` time.

---
## 💡 Logic
- Use `sum` to track the current subarray sum.
- If `sum < 0`, reset it to `0`.
- Track the overall maximum using `maxSum`.
---
## 🧠 Formula

 ```cpp
sum += x;
maxSum = max(maxSum, sum);
sum = max(sum, 0);
```
---
## 💻 Code (C++)

 ```cpp
int maxSubArray(vector<int>& nums) {
    int maxSum = nums[0], sum = 0;
    for (int x : nums) {
        sum += x;
        maxSum = max(maxSum, sum);
        sum = max(sum, 0);
    }
    return maxSum;
}
```
---
## 📌 Example

**Input**:
 ```cpp
[-2, 1, -3, 4, -1, 2, 1, -5, 4]
```

**Output**:  
`6` → from subarray `[4, -1, 2, 1]`

---
## 📝 Notes

- Handles all-negative arrays (initialize `maxSum = nums[0]`).
- Can be extended to:
  - Return the actual subarray.
  - Handle circular arrays.
  - 2D version for matrices.