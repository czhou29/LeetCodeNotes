## 217 Contains Duplicate

```c++
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_set<int> x;
        for(auto a: nums){
            if(x.count(a)) return true;
            else x.insert(a);
        }
        return false;
    }
};
```

