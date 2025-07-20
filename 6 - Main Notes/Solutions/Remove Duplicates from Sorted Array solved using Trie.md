**Topic:** [[Trie]] [[String]]
**Problem:**  [[Remove Duplicates from Sorted Array]]
**Last Modified:**  `2025-07-20 11:48`

 $TC: O(n * l)$ *l is the length of each word*
 $SC: O(n)$

---
##### **Intuition**: Traverse from right side. exclude the the last sub folder and search if found break

 
```cpp
struct TrieNode {
    TrieNode *children[27];  // 26 for letters 'a' to 'z' and 1 for '/'
    bool isEndOfWord;

    TrieNode() {
        isEndOfWord = false;
        for (int i = 0; i < 27; i++) {
            children[i] = nullptr;
        }
    }
};

class Trie {
private:
    TrieNode *root;

public:
    Trie() { root = new TrieNode(); }

    void insert(const string &word) {
        TrieNode *node = root;
        for (char c : word) {
            int index;
            if (c == '/') {
                index = 26;  // Treat '/' as the 27th position
            } else {
                index = c - 'a';
            }
            if (!node->children[index]) {
                node->children[index] = new TrieNode();
            }
            node = node->children[index];
        }
        node->isEndOfWord = true;
    }

    bool search(const string &word) {
        TrieNode *node = root;
        for (char c : word) {
            int index;
            if (c == '/') {
                index = 26;
            } else {
                index = c - 'a';
            }
            if (!node->children[index]) return false;
            node = node->children[index];
        }
        return node->isEndOfWord;
    }
};

class Solution {
public:
    vector<string> removeSubfolders(vector<string> &folder) {
        Trie T;
        vector<string> ans;
        for (string &s : folder) T.insert(s);
        for (string &s : folder) {
            string subSt = "";
            for (int i = s.length() - 1; i >= 0; i--) {
                if (s[i] == '/') {
                    subSt = s.substr(0, i);
                    if (T.search(subSt)) break;
                }
            }
            if (!subSt.length()) ans.push_back(s);
        }
        return ans;
    }
};
```
