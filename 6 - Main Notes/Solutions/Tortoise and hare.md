**Topic:**  [[Two Pointers]]
**Problem:**  [[Linked List Cycle]]
**Last Modified**: `2025-05-11 20:39`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**:  **Tortoise** will run *slow* and **hare** will run *fast* if list is cyclic they will meet at some point. 
 
```cpp
tortoise = hare = head;
while (hare != NULL && hare->next != NULL) {
	tortoise = tortoise->next;
    hare = hare->next->next;

    //if list is cyclic tortoise will meet hare some point
    if (tortoise == hare)  return true;

}
return false;
```


