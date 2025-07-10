🟢 Pros of **Denormalization**

1. Improved *query performance*. (No Joins)
2. Simplified query
3. Reduce joins
4. Read intensive scenarios ---> *Best*

🔴 Cons of **Denormalization**
1. **Redundancy** ---> Memory waste
2. Inconsistent Data *(Suppose your forgot to update Department Location of HR in some row)*
3. **Update/Write** operations ---> Extremely slow because you will have to update in multiple places. (Redundant)