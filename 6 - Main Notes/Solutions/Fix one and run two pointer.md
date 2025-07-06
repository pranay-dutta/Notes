**Topic:** [[Two Pointers]] [[Array]]
**Problem:**  [[3Sum Closest]]
**Last Modified:**  `2025-07-07 01:40`

 $TC: O(n^2)$
 $SC: O(1)$

---
**Intuition**: fix one pointer **k** and from **(i=k+1)** to **(j=n-1)** do **two pointer** and try to reduce the **closest sum**
`!Importan` *there will be always only solution*  suppose target = 3 either closest would (....-2.. 3. or .................3...................... )

 
```cpp
int threeSumClosest(vector<int>& nums, int target) {
	int n = nums.size(), closestSum = 1e9;

	sort(begin(nums), end(nums));

	for (int k = 0; k <=n-3; k++) {
		int i=k+1, j=n-1;

		while(i < j) {
			int sum = (nums[k]+nums[i]+nums[j]);

			if(abs(target-sum) < abs(target-closestSum)) { //if new sum is closer to target update closestSum
				closestSum = sum;
			}

			if(sum < target) i++; //if sum is less try to make it close to target
			else j--;  //else sum is high try to reduce it
		}
	}
	return closestSum;
}
```

