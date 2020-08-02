## 647 Palindromic Substrings

```c++
class Solution {
public:
    int countSubstrings(string s) {
        int res = 0;
        for(int i = 0; i < s.size(); i++) {
            for(int j = i, k = i; j>=0 && k < s.size(); j--, k++) {
                if(s[j] == s[k]) res++;
                else break;
            }
            for(int j = i, k = i+1; j>=0 && k < s.size(); j--, k++) {
                if(s[j] == s[k]) res++;
                else break;
            }
        }
        return res;
    }
};
```

