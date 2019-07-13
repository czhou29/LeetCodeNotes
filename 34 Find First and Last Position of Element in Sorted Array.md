## 34 Find First and Last Position of Element in Sorted Array

```c++
class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        if(nums.empty()) return vector<int> {-1, -1};
        int l = 0, r = nums.size() - 1;
        while(r>l){
            int mid = l + r >> 1;
            if(nums[mid] >= target) r = mid;
            else l = mid + 1;
        }
        if(nums[l]!=target) return vector<int> {-1, -1};
        vector<int> res;
        res.push_back(l);
        l = 0, r = nums.size() - 1;
        while(r>l){
            int mid = (l + r + 1) >> 1;
            if(nums[mid] <= target) l = mid;
            else r = mid - 1;
        }
        res.push_back(l);
        return res;
    }
};
```

