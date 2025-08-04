**Topic:** [[Binary Search on Answer]]
**Problem:**  [[Minimum Number of Days to Make m Bouquets]]
**Last Modified:**  `2025-08-05 02:10`

 $TC: O(n\ log(n))$
 $SC: O(1)$

---
##### **Intuition**: binary search on **bloomday** and check if it's possible on the i'th day to make 'm' bouquests

 
```cpp
bool isPossible(vector<int>& bloomDay, int curDay,  int bouquetsRequired, int flowerReqEachBouquet) {
	int count = 0, bouquetsMade = 0;

	for(int i = 0; i < bloomDay.size();  i++) {
		if(bloomDay[i] <= curDay) count++; //if i'th flower's bloom day is less it's bloomed
		else count = 0; //have to take adjacent flowers, so reset the count if not adjacent flower found

		if(count == flowerReqEachBouquet) {
			count = 0;
			bouquetsMade += 1; //made a bouquet by taking adjacent flower/
		}
		if(bouquetsMade == bouquetsRequired) break;
	}
	return bouquetsMade >= bouquetsRequired;
}

int minDays(vector<int>& bloomDay, int m, int k) {
	int n = bloomDay.size();
	if((long)m*k > n) return -1;

	int mini = INT_MAX, maxi = 0;
	for(int i = 0; i < n; i++) {
		mini=min(mini, bloomDay[i]); 
		maxi=max(maxi, bloomDay[i]);
	}

	int ans = -1;
	while(mini <= maxi) {
		int mid = mini + (maxi - mini) / 2;

		if(isPossible(bloomDay, mid, m, k)) {
			ans = mid;
			maxi = mid-1;
		}
		else mini = mid + 1;
	}
	return ans;
}
```

