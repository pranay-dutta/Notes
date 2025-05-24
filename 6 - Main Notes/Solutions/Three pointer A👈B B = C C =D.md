**Topic:**  [[Reverse]]
**Problem**:  [[Reverse Linked List]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: A <--- B  B moves to C  C moves to D in 

<img src="three-pointers-linked-list.png" style="border-radius: 10px" alt="Landscape Image" width="400" height="auto"/>
 
```cpp
current = prev = nextNode = head;
nextNode = head->next;
while(nextNode) { //TC: O(n) SC: O(1)
	prev = current;
	current = nextNode;

	nextNode = nextNode->next;
	current->next = prev;
}

head->next = NULL;      //head became lastNode so he doesn't point anywhere
return current;
```
