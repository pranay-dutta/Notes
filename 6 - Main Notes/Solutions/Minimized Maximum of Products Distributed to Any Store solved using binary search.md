**Topic:** [[Binary Search]] [[Binary Search on Answer]]
**Problem:**  [[Minimized Maximum of Products Distributed to Any Store]]
**Last Modified:**  `2025-08-05 14:48`

 $TC: O(n\log(n))$
 $SC: O(1)$

---
##### **Intuition**: take *max quantity* as highest and try to reduce it such that all *stores* receives a type of product

 
```cpp
bool isPossibleToDistribute(int numOfStores, int curQty, vector<int>& quantities) {
	for(int q: quantities) {
		int storesGiven = (q + curQty - 1) / curQty; //ceil function
		numOfStores -= storesGiven;

		if(numOfStores < 0) return false; //if given to more stores than the number of stores return
	}
	return true;
}
int minimizedMaximum(int n, vector<int>& quantities) {
	int l = 1;
	int r = *max_element(begin(quantities), end(quantities));

	int ans = INT_MAX;
	while(l <= r) {
		int mid = l + (r-l) / 2;
		if(isPossibleToDistribute(n, mid, quantities)) {
			ans = min(ans, mid);
			r = mid-1;
		} else {
			l = mid+1;
		}
	}
	return ans;
}
```