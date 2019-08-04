## 165 Compare Version Numbers

```c++
class Solution {
public:
    int compareVersion(string v1, string v2) {
        int p1 = 0, p2 = 0;
        int n1 = 0, n2 = 0;
        while(p1 < v1.size() || p2 < v2.size()) {
            while(p1 < v1.size() && v1[p1] != '.'){
                n1 = 10 * n1 + v1[p1] - '0';
                p1++;
            }
            while(p2 < v2.size() && v2[p2] != '.'){
                n2 = 10 * n2 + v2[p2] - '0';
                p2++;
            }
            if(n1 > n2) return 1;
            else if(n1 < n2) return -1;
            n1 = 0, n2 = 0;
            p1++, p2++;
        }
        return 0;
    }
};
```

