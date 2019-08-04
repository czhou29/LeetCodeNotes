## 5 Longest Palindromic Substring

```c++
class Solution {
public:
    string longestPalindrome(string s) {
        int res = 0;
        string str;
        for(int i = 0; i < s.size(); i++) {
            for(int j = i, k = i; j >= 0 && k < s.size(); j--, k++) {
                if(s[j] == s[k]) {
                    if(k-j + 1 > res) {
                        res = k-j + 1;
                        str = s.substr(j, k-j + 1);
                    }
                }
                else break;
            }
            
            for(int j = i, k = i + 1; j >= 0 && k < s.size(); j--, k++) {
                if(s[j] == s[k]) {
                    if(k-j+1 > res) {
                        res = k-j+1;
                        str = s.substr(j, k-j+1);
                    }
                }
                else break;
            }
        }
        return str;
    }
};
```

