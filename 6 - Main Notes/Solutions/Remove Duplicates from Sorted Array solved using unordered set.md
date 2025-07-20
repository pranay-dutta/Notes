**Topic:** [[Trie]] [[String]]
**Problem:**  [[Remove Duplicates from Sorted Array]]
**Last Modified:**  `2025-07-20 11:48`

 $TC: O(n * l)$ *l is the length of each word*
 $SC: O(n)$

---
##### **Intuition**: Traverse from right side. exclude the the last sub folder and search if found break

 
```cpp
class Solution {
public:
    vector<string> removeSubfolders(vector<string>& folder) {
        unordered_set<string> se;
        for(string& path: folder) se.insert(path);

        vector<string> ans;

        for(string& path: folder) {
            string subStr = "";

            for(int i = path.length()-1; i >= 0; i--) {
                if(path[i]=='/') {
                    subStr = path.substr(0, i);
                    if(se.count(subStr)) break;
                }
            }
            if(!subStr.length()) ans.push_back(path);
        }
        return ans;
    }
};
```

