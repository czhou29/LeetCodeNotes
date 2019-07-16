## 389 Find the Difference

```c++
class Solution {
public:
    char findTheDifference(string s, string t) {
        int is = 0, it = 0;
        for(char c: s) is+=c-'a';
        for(char c: t) it+=c-'a';
        return char(abs(is-it)+'a');
    }
};
```

