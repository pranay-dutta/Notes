**Topic:** [[Binary Search]] [[Binary Search on Answer]]
**Problem:**  [[Koko Eating Bananas]]
**Last Modified:**  `2025-08-05 14:37`

 $TC: O(n\log(n))$
 $SC: O(1)$

---
##### **Intuition**: chose the **max** pile and try to reduce the pile to get minimum pile that can exhaust the all the bananas in **h** hours

 
```cpp
bool isEatable(vector<int>& piles, int bananaPerHr, int hours) {
	for(int pile: piles) {
		hours -= (pile + bananaPerHr-1) / bananaPerHr; //ceil function
		if(hours < 0) return false; //if more than given hour taken, return
	}
	return true;
}

int minEatingSpeed(vector<int>& piles, int h) {
	int l = 1;
	int r = *max_element(begin(piles), end(piles));

	int minimumPile = INT_MAX;
	while(l <= r) {
		int mid = l + (r-l) / 2;
		if(isEatable(piles, mid, h)) { //try to reduce the banana ate per hour
			minimumPile = min(minimumPile, mid); 
			r = mid-1;
		} else {
			l = mid + 1;
		}
	}
	return minimumPile;
}
```

