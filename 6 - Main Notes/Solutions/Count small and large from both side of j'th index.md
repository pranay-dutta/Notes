**Topic:** [[Dynamic Programing]] 
**Problem:**  [[Count Number of Teams]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n²)$
 $SC: O(1)$

---
##### **Intuition**: finding all *smaller* and *larger* elements from **left** and and *smaller* and *larger* from **right**

 
```cpp
for (int j = 1; j < n - 1; j++) {
	int smallerLeft = 0;
    int largerLeft = 0;
    
    int smallerRight = 0;
    int largerRight = 0;

    // left side's smaller and larger element;
    for (int i = 0; i < j; i++) {
        if (rating[i] < rating[j]) smallerLeft++;
		if (rating[i] > rating[j]) largerLeft++;
	}
	// right side's smaller and larger element;
    for (int k = j + 1; k < n; k++) {
	    if (rating[k] < rating[j]) smallerRight++;
        if (rating[k] > rating[j]) largerRight++;
	}

    teamCount += largerLeft * smallerRight;
    teamCount += smallerLeft * largerRight;
}
return teamCount;
```

```cpp
int numTeams(vector<int>& rating) {
	const int n = rating.size();
	int teamCnt=0;

	for(int i=1; i <=n-2; i++) {
		int L[2]={0}, R[2]={0};

		for(int j=0; j<i; j++) 
			L[rating[j] < rating[i]]++; //if true increase 
			
		for(int k=i+1; k<n; k++) 
			R[rating[k] < rating[i]]++;
		
		//number of valid teams can be formed
		teamCnt += L[0]*R[1] + L[1]*R[0];
	}
	return teamCnt;
}
```


