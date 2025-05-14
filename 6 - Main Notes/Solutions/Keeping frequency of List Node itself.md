**Topic:** [[Hash Table]]
**Problem:**  [[Linked List Cycle]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n)$
 $SC: O(n)$

---
##### **Intuition**:  Keeping frequency of each **Node** if frequency is already **1** that means **pointer** cycled to same node
 
```cpp
unordered_map<ListNode*, int> mp; //ListNode* frequency
while(temp) {
	//if frequncy is not 0 means pointer traversed to same node again
	if(mp[temp] != 0) return true; 

	else{
	    mp[temp]++; //increase frequncy
	    temp = temp->next;
	} 
}
return false;
```



