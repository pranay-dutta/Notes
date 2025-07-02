**Topic:** [[Design]]
**Problem:**  [[Insert Delete GetRandom O(1)]]
**Last Modified:**  `2025-07-03 01:47`

 $TC: O(1)$
 $SC: O(2n)$

---
##### **Intuition**: create an array to store element and map to store index of those elements

 
```cpp
class RandomizedSet {
private: 
    vector<int> v;
    unordered_map<int, int> mp; //mp<number, index> mp

    bool found(int val) {
        return mp.find(val) != mp.end();
    }
    
public:
    RandomizedSet() {}

    bool insert(int val) {
        if(found(val)) return false;

        v.push_back(val);
        mp[val] = v.size()-1; //index
        return true;
    }

    bool remove(int val) {
        if(!found(val)) return false; //can't remove unknown value

        auto [e, index] = *mp.find(val); //destructured

        v[index] = v.back(); //val inside vec got replaced with last element of vec 
        v.pop_back(); //removed last element

        mp[v[index]] = index; //new index added 
        mp.erase(val); //erase the value from the map

        return true;
    }

    int getRandom() {
        return v[rand()%v.size()];
    }
};
```

