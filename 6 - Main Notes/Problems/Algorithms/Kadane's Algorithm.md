Goal:
-----
Find the maximum sum of a contiguous subarray in O(n) time.

Logic:
------
- Use `sum` to track the current subarray sum.
- If `sum < 0`, reset it to 0.
- Keep track of the maximum sum seen so far (`maxSum`).

Formula:
--------
sum += x;
maxSum = max(maxSum, sum);
sum = max(sum, 0);

Code (C++):
--------

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
-----------

Example:
Input:  [-2, 1, -3, 4, -1, 2, 1, -5, 4]
Output: 6 → from subarray [4, -1, 2, 1]

Notes:
------
- Works even if all numbers are negative.
- Always initialize maxSum = nums[0] to handle negative-only arrays.
- Can be extended to return the subarray or handle circular arrays.
