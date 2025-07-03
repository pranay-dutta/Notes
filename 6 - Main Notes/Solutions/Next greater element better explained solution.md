**Topic:** [[Two Pointers]]
**Problem:**  [[Next Permutation]]
**Last Modified:**  `2025-07-03 11:58`

 $TC: O(n)$
 $SC: O(n)$

---
##### **Intuition**: find the pivot, fine the smallest greater element after pivot index.

 
```cpp
	//⚠️Get pivot, get nextGreterElementIndex, swap, reverse
	
    int nextGreater(int smElem, int nxtGrtrElemIdx, vector<int>& nums) {
        int i = 0;
        while (nxtGrtrElemIdx < nums.size()) { //find the next greater elemnt till end || see the optimal appraoch for another type
            if (smElem < nums[nxtGrtrElemIdx]) i = nxtGrtrElemIdx;
            nxtGrtrElemIdx++;
        }
        return i; 
    }
	
    void nextPermutation(vector<int>& nums) {
        int n = nums.size(), pivot = -1;
        
        for (int i=n-1; i>0; i--) { 
            if (nums[i]>nums[i-1]) {  
                pivot = i-1; break;
            }
        }

        if(pivot>=0) {
            int nxtGreaterIdx = nextGreater(nums[pivot], pivot+1, nums);
            swap(nums[pivot], nums[nxtGreaterIdx]);
        }

        reverse(begin(nums) + pivot+1, end(nums));
        return;
    }
```

