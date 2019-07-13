## 153 Find Minimum in Rotated Sorted Array

```c++
class Solution {
public:
    int findMin(vector<int>& nums) {
        int l = 0, r = nums.size() - 1;
        int left = nums[l], right = nums[r];
        while(r>l){
            int mid = (l + r)/2;
            if(nums[mid] <= left && nums[mid] <= right) r = mid;
            else l = mid + 1;
        }
        if (nums[r] < nums[0]) return nums[r];
        else return nums[0];
    }
};
```

