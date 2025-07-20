**Topic:** [[Sliding Window]]  [[Array]]
**Problem:**  [[Grumpy Bookstore Owner]]
**Last Modified:**  `2025-07-20 22:50`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: calculate sum of total satisfaction before applying control, then apply Control and slide the window to get the most customers who is Satisfied
 
```cpp
int maxSatisfied(vector<int>& customers, vector<int>& grumpy, int minutes) {
	int n = grumpy.size();
	int totalSatisfaction = 0;
	
	//1. Get the sum of totalSatisfaction statisfaction without using control technique
	for(int i = 0; i < n; i++) {
		if(grumpy[i]==0) totalSatisfaction += customers[i];
	}

	int withoutControl = 0, withControl = 0;
	int res = 0, i = 0, j = 0;

	//2. Slide the window of 'minutes' size and maximize the satisfaction
	while(j < n) {
		int windowSize = j - i;

		if(windowSize < minutes) {
			withoutControl += grumpy[j] ? 0 : customers[j];
			withControl += customers[j];
			j++;
		} else {
			withoutControl -= grumpy[i] ? 0 : customers[i];
			withControl -= customers[i];
			i++;
		}

		res = max(res, totalSatisfaction - withoutControl + withControl);
	} 
	return res;
}
```

