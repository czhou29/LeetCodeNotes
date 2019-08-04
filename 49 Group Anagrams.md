## 49 Group Anagrams

```c++
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
        unordered_map<string, vector<string>> m;
        for(auto &s: strs){
            string t = s;
            sort(t.begin(), t.end());
            m[t].push_back(s);
        }
        vector<vector<string>> res;
        for(auto i = m.begin(); i != m.end(); i++) {
            res.push_back(i->second);
        }
        return res;
    }
};
```

