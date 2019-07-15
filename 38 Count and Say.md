## 38 Count and Say

```c++
class Solution {
public:
    string countAndSay(int n) {
        string res = "1";
        for(int i = 2; i <= n; i++) {
            string nr = "";
            for(int j = 0; j < res.size();) {
                int t = j;
                while(t < res.size() && res[t] == res[j]) t++;
                nr += to_string(t - j) + res[j];
                j = t;
            }
            res = nr;
        }
        return res;
    }
};
```

