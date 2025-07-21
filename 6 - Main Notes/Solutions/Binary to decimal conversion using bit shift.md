**Topic:** [[Bit Manipulation]]
**Problem:**  [[Convert Binary Number in a Linked List to Integer]]
**Last Modified:**  `2025-07-15 02:24`

 $TC: O(n)$
 $SC: O(1)$

---
##### **Intuition**: left shift zero by 1 each time and compare with current bit in linked list

<img src="bits-linked-list.png" width="100%" style="border-radius: 10px; max-width: 300px" />
 
```cpp
    int getDecimalValue(ListNode* head) {
        int result = 0;
        
        while (head) {
            result = (result << 1) | head->val; 
			// 0 << 1 == 0 
			//           1 //first node in ll
			
			// 1 << 1 == 10 
			//            0 //second node in ll
			
			// 10 << 1 === 100
			//               1 //third node in ll
			// 101 = 5
            head = head->next;
        }
        return result;
    }
}
```

