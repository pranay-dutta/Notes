**Topic:** [[4 - Index/Two Pointers]]
**Problem:**  [[Squares of a Sorted Array]]
**Last Modified:**  `2025-05-13 20:04`

 $TC: O(n)$
 $SC: O(1: exculding-res)$

---
##### **Intuition**: keep two pointers: at the start and end. 
 *arr* is sorted [-4, 2,3,7] so the first and last squre is to compare, and add to end

 
```cpp
s=0, e=n-1, crawler=n-1
res(n)

for(i=0;i<n) { 
	sSq=nums[s]*nums[s]
	eSq=nums[e]*nums[e]

	//compare and add to the end
	res[crawler--] = max(sSq, eSq)
	
	//which value is used move it's pointer
	sSq>eSq ? s++ : e--; 
}
```

