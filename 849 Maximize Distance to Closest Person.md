## 849 Maximize Distance to Closest Person

```c++
class Solution {
public:
    int maxDistToClosest(vector<int>& seats) {
        int n = seats.size();
        int last = -1, ans = -1;
        for(int i = 0; i < n; i ++){
            if(seats[i] == 1) {
                if(ans == -1) ans = i;
                else ans = max(ans, (i-last) / 2);
                last = i;
            }
        }
        ans = max(ans, n-1-last);
        return ans;
    }
};
```

