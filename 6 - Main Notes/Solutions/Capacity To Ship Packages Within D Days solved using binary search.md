**Topic:** [[Binary Search on Answer]] [[Binary Search]]
**Problem:**  [[Capacity To Ship Packages Within D Days]]
**Last Modified:**  `2025-08-05 02:19`

 $TC: O(n\log(n))$
 $SC: O(1)$

---
##### **Intuition**:  Do the binary search on Capacity that will be shipped on Each day

 
```cpp
bool isPossibleToShip(vector<int>& weights, int capacity, int days) {
	int took = 0; //count of parcel took for each day

	for(int i = 0; i < weights.size();) {
		if(days <= 0) return false;

		if(took + weights[i] <= capacity) {
			took += weights[i];
			i++;

		} else {
			took = 0;
			days--;
		}
	}
	return true;
}
int shipWithinDays(vector<int>& weights, int days) {
	int n = weights.size();
	int l = 0;
	int r = accumulate(begin(weights), end(weights), 0);

	int minDays = INT_MAX;
	while(l <= r) {
		int estCapacity = l + (r-l) / 2;

		if(isPossibleToShip(weights, estCapacity, days)) {
			minDays = min(minDays, estCapacity);
			r = estCapacity - 1;
		} else {
			l = estCapacity + 1;
		}
	}
	return minDays;
}
```

