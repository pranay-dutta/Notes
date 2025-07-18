**Topic:** [[Trie]]
**Problem:**  [[Implement Trie (Prefix Tree)]]
**Last Modified:**  `2025-07-19 00:57`

 $TC: O(L)$
 $SC: O(L * 26)$

---
#### **Intuition**: a node having 26 links = `[a.....z]`

 
```cpp
//TC: O(L)
//SC: O(L * 26)
class TrieNode {
private:
    bool wordEnd;
    vector<TrieNode*> children;
public:

    TrieNode() : children(26, nullptr), wordEnd(false) {}

    bool containsKey(char ch) {
        return children[ch-'a'] != nullptr;
    }

    void put(char ch, TrieNode* node) {
        children[ch-'a'] = node;
    }
    TrieNode* get(char ch) {
        return children[ch-'a'];
    }

    void setWordEnd(bool flag) {
        wordEnd = flag;
    }
    bool getWordEnd() {
        return wordEnd;
    }


};

class Trie {
    TrieNode* root;

public:
    Trie() { root = new TrieNode(); }

    void insert(string word) { //O(L) : word length
        TrieNode* crawler = root;
        
        for (char ch : word) {
            if (!crawler->containsKey(ch)) {
                crawler->put(ch, new TrieNode());
            }
            crawler = crawler->get(ch);
        }
        crawler->setWordEnd(true);
    }

    bool search(string word) { //O(L) : word length
        TrieNode* crawler = root;
        for (char ch : word) {
            if (!crawler->containsKey(ch)) return false;
            crawler = crawler->get(ch);
        }
        if (crawler->getWordEnd()) return true; //if word end return true
        return false;
    }

    bool startsWith(string prefix) { //O(L) :prefix length
        TrieNode* crawler = root;
        for (char ch : prefix) {
            if (!crawler->containsKey(ch)) return false;
            crawler = crawler->get(ch);
        }
        return true;
    }
};

/**
 * Your Trie object will be instantiated and called as such:
 * Trie* obj = new Trie();
 * obj->insert(word);
 * bool param_2 = obj->search(word);
 * bool param_3 = obj->startsWith(prefix);
 */


```

