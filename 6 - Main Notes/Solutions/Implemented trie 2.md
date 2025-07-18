**Topic:** [[Trie]]
**Problem:**  [[Implement Trie 2]]
**Last Modified:**  `2025-07-19 01:04`

 $TC: O()$
 $SC: O()$

---
##### **Intuition**: upgrade trie1 and just keep a counter of each letter(Trie node) and (Word End)

 
```cpp
struct TrieNode {

  TrieNode *children[26];

  int cntEndWith = 0;

  int cntPrefix = 0;

  

  bool containsKey(char ch) {

    return children[ch - 'a'] != NULL;

  }

  

  TrieNode* get(char ch) {

    return children[ch - 'a'];

  }

  void put(char ch, TrieNode* node) {

    children[ch - 'a'] = node;

  }

  

  void increaseEnd() {

    cntEndWith++;

  }

  void increasePrefix () {

    cntPrefix++;

  }

  

  void deleteEnd() {

    cntEndWith--;

  }

  void reducePrefix() {

    cntPrefix--;

  }

  int getEnd() {

    return cntEndWith;

  }

  int getPrefix() {

    return cntPrefix;

  }

};

class Trie {

private:

  TrieNode* root;

public:

  Trie() {

    root = new TrieNode();

  }

  void insert(string& word) {

    TrieNode* crawler = root;

    for (char ch : word) {

      if (!crawler->containsKey(ch)) {

        crawler->put(ch, new TrieNode());

      }

      crawler = crawler->get(ch);

      crawler->increasePrefix();

    }

    crawler->increaseEnd();

  }

  int countWordsEqualTo(string& word) {

    TrieNode* crawler = root;

    for (char ch : word) {

      if (!crawler->containsKey(ch)) {

        return 0;

      }

      crawler = crawler->get(ch);

    }

    return crawler->getEnd();

  }

  int countWordsStartingWith(string& prefix) {

    TrieNode* crawler = root;

    for (char ch : prefix) {
      if (!crawler->containsKey(ch)) {
        return 0;
      }
      crawler = crawler->get(ch);
    }
    return crawler->getPrefix();
  }

  void erase(string& word) {
    TrieNode* crawler = root;
    for (char ch : word) {
      if (!crawler->containsKey(ch))  return;
      crawler->reducePrefix();
    }
    crawler->deleteEnd();
  }

```

