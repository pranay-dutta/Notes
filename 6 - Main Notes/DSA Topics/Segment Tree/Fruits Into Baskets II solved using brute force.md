**Topic:** [[Brute Force]]
**Problem:**  [[Fruits Into Baskets II]]
**Last Modified:**  `2025-08-08 13:47`

 $TC: O(n^2)$
 $SC: O(1)$

---
##### **Intuition**: start putting from Left basket if you put in i'th basket mark it as full by -1
 
```cpp
int numOfUnplacedFruits(vector<int>& fruits, vector<int>& baskets) {

	int fruitTypeUsed = 0;
	int n = fruits.size();

	for(int i = 0; i < n; i++) {
		for(int j = 0; j < n; j++) {
			if(baskets[j] >= fruits[i]) { 
				baskets[j] = 0;
				fruitTypeUsed += 1;
				break;
			}
		}
	}
	return fruits.size() - fruitTypeUsed;
}
```

