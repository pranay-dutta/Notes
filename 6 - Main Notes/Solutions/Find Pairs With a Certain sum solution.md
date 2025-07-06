**Topic:** [[Design]]
**Problem:**  [[Finding Pairs With a Certain Sum]]
**Last Modified:**  `2025-07-07 01:22`

 $TC: O(n)$
 $SC: O(n + m + k)$

---
##### **Intuition**: store v2 array, create unordered map v1, mp; Do complement search just like two sum.
`pairs += f[n[i]] * f2[tot-n[i]]//complement `

 
```cpp
class FindSumPairs {
private: 
    vector<int> v2;
    unordered_map<int,int> v1, mp;
	
public:
    FindSumPairs(vector<int>& n1, vector<int>& n2) {
        v2 = nums2;

        for(int& x: n1) v1[x]++;
        for(int& x: n2) mp[x]++;
    }
    
    void add(int index, int val) {
        int x = v2[index];
        mp[x]--; 
        v2[index] += val; //keep v2 in sync
        mp[x+val]++;
    }
    
    int count(int tot) {
        int pairs = 0;

        for(auto& [e, f]: v1) {
            int complement = tot-e;
            pairs += f * mp[complement];
        }
        return pairs;
    }
};
```

