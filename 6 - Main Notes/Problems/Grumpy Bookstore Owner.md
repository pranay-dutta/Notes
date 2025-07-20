**Topic:**  [[Sliding Window]] [[Array]]
**Last Modified**:  `2025-07-20 22:41`
#editpending  #addbruteforce

`Problem: `

```
parameters:
vector<int>& grumpy, vector<int>& customers, int minutes

customers[i] represents number of customers at i'th minute
grumpy[i] represents store owner is grumpy or not at i'th minute (1 = grumpy 0 = not grumpy)

grumpy[i] == 0 then number of customers at i'th min (customers[i]) is statisfied

You'll get param: minutes where store owner can keep him calm for consecutive minutes

Try to maximize the statisfied customers

!note: customer[i] enters at i'th minute and leaves at end of i't minute
```

### Solutions -- 

###### 🟢 Best
 `Time O() Space O()` [[Grumpy Bookstore Owner solved using sliding window]]
----------------------------------------------------------------------------------------------
###### 🟡 Average
 `Time O() Space O()` 
----------------------------------------------------------------------------------------------
###### 🔴 Worst
 `Time O(n^2) Space O(1)`  [[]]
----------------------------------------------------------------------------------------------

