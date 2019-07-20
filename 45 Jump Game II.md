## 45 Jump Game II

```c++
class Solution {
public:
    int jump(vector<int>& nums) {
        int last = 0, n = nums.size();
        vector<int> f(n);
        f[0] = 0;
        for(int i = 1; i < n; i++) {
            while(i > last + nums[last])
                last++;
            f[i] = f[last] + 1;
        }
        return f[n-1];
    }
};
```

