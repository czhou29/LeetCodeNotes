## 17 Letter Combinations of a Phone Number

```c++
class Solution {
public:
    vector<string> letterCombinations(string digits) {
        if (digits.empty()) return vector<string>();
        string chars[] = {"abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"};
        
        vector<string> res(1, "");
        
        for(auto d: digits) {
            vector<string> now;
            for(auto c: chars[d-'2']) {
                for(auto r: res) {
                    now.push_back(r+c);
                }
            }
            res = now;
        }
        return res;
    }
};
```

