## 13 Roman to Integer

```c++
class Solution {
public:
    int romanToInt(string s) {
        if(s.size() == 0) return 0;
        unordered_map<char, int> map;
        map['I'] = 1;
        map['V'] = 5;
        map['X'] = 10;
        map['L'] = 50;
        map['C'] = 100;
        map['D'] = 500;
        map['M'] = 1000;
        int res = 0;
        for(int i = 0; i < s.size()-1; i++) {
            res = map[s[i]] < map[s[i+1]] ? (res-map[s[i]]) : (res+map[s[i]]);
        }
        res += map[s[s.size()-1]];
        return res;
    }
};
```

