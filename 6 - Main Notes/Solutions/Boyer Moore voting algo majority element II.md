**Topic:** [[Boyer Moore Voting Algorithm]]
**Problem:**  [[Majority Element II]]
**Last Modified:**  `2025-05-13 23:29`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: for any *(n/k)* division there will be *(k-1)* majority element. So the major party will dominate

 
```cpp
//m majority element
//c count
m1=0,m2=0, c1=0, c2=0

//1. find candidates
for(x: nums) { //first check for major party
	if (m1==x) c1++
	else if(m2==x) c2++
	else if(c1==0) m1=x, c1=1 //new m1 found
	else if(c2==0) m2=x, c2=1 //new m2 found
	else c1--, c2--;
}

//2. verfiy candidates
c1=0, c2=0
for(x: nums) {
	if(m1==x) c1++
	else if(m2==x) c2++
}

//3. prepare the result
if(c1>floor(n/3)) res.push_back(m1)
if(c2>floor(n/3)) res.push_back(m2)

return res;

```

