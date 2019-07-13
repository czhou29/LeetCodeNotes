##41 First Missing Positive

```c++
class Solution {
public:
    int firstMissingPositive(vector<int>& nums) {
        int n = nums.size();
        // 桶排序 对每一个数在范围内（正数且小于等于n） 看一看是不是在对应的位置上，如果不是一直换
        for(int i = 0; i < n; i++)
            while(nums[i] > 0 && nums[i] <= n && nums[nums[i]-1] != nums[i])
                swap(nums[i], nums[nums[i]-1]);
        // 看第一个不在对应位置上的数
        for(int i = 0; i < n; i++)
            if(nums[i] != i+1)
                return i+1;
        
        return n+1;
    }
};
```

