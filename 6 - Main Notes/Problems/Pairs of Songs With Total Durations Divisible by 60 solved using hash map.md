**Topic:** [[Array]] [[Hash Table]]
**Problem:**  [[Pairs of Songs With Total Durations Divisible by 60]]
**Last Modified:**  `2025-07-16 00:32`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: store the modulus version of every time and check the complement

 
```cpp
int numPairsDivisibleBy60(vector<int>& time) {
	vector<int> t(60, 0);
	long long pairs = 0;

	for(int& x: time) t[x%60]++;

	for(int i=1; i<30; i++) {
		pairs += (long long)t[i] * t[60-i];
	}
	pairs += ((long long)t[0]  * (t[0]-1))/2;  //[0,0,0] = 3*(3-1) = 6/2 = 3
	pairs += ((long long)t[30] * (t[30]-1))/2; //[30,30,30] = 3*(3-1) = 6/2 =3
	
	
	return (int)pairs;
}
```

