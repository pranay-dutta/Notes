**Topic:** [[Cumulative Sum]] [[Sliding Window]]
**Problem:**  [[Maximum Points You Can Obtain from Cards]]
**Last Modified:**  `2025-07-23 01:13`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: calculate sum of first window from index 0, then slide the window left to get ending elements
 
```cpp
int maxScore(vector<int>& cardPoints, int k) {
	int n = cardPoints.size();
	int lSum = 0;

	//1. Calculate sum of first window
	for (int i = 0; i < k; i++) {
		lSum += cardPoints[i];
	}

	int maxPoints = lSum; //assume first window is having maxPoints
	int rSum = 0;

	//2. Slide the window to the left to get end element
	for(int i = k-1, j = n-1; i >= 0; i--, j--) {
		lSum -= cardPoints[i]; //exclude
		rSum += cardPoints[j]; //include

		maxPoints = max(maxPoints, lSum + rSum);
	}
	return maxPoints;
}
```
