Floyd's Cycle Detection Algorithm is used to detect cycles in a linked list or in sequences.

--- 
### Some problems on cycle detection 

- [[Linked List Cycle]] 
- [[Find the Duplicate Number]]

### 🔁 **Concept**:
It uses two pointers:

- 🐢 **Tortoise (slow)** – moves 1 step at a time
- 🐇 **Hare (fast)** – moves 2 steps at a time

### 🧠 **How it works**:

1. Both start at the head.
2. If there is a cycle, the fast pointer will eventually "lap" the slow pointer inside the cycle (they meet).
3. If there’s no cycle, the fast pointer reaches `null`.

### 🧩 **To find the cycle start**:

- After they meet, reset one pointer to head.
- Move both pointers 1 step at a time.
- The point they meet again is the **start of the cycle**.

### ✅ **Time Complexity**: O(n)
### ✅ **Space Complexity**: O(1)

It's efficient and commonly used in problems like detecting cycles in linked lists.

