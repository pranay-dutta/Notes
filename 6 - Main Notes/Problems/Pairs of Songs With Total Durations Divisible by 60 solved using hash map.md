**Topic:** [[Array]] [[Hash Table]] [[Math]]
**Problem:**  [[Pairs of Songs With Total Durations Divisible by 60]]
**Last Modified:**  `2025-07-16 00:32`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: store the modulus version of every time and check the complement

`1 <= time[i] <= 500`

`Formula: nC2 = (n*n-1)/2`

```cpp
int numPairsDivisibleBy60(vector<int>& time) {
	vector<int> t(60, 0);
	long long pairs = 0;

	for(int& x: time) t[x%60]++; //0-59

	for(int i=1; i<30; i++) { 
	️⚠️/* only run from 1 to 29 very important 
		because 60%60 = 0 and 30%60 = 30
		both 0 & 30's complement is they, themselvs 
	*/
		pairs += (long long)t[i] * t[60-i];
	}
	
	//NC2
	pairs += ((long long)t[0]  * (t[0]-1))/2;  //[0,0,0] = 3*(3-1) = 6/2 = 3 (nc2)
	pairs += ((long long)t[30] * (t[30]-1))/2; //[30,30,30] = 3*(3-1) = 6/2 =3 (nc2)
	
	
	return (int)pairs;
}
```

