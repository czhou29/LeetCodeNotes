## 33 Search in Rotated Sorted Array

```c++
class Solution {
public:
    int search(vector<int>& nums, int target) {
        if(nums.empty()) return -1;
        int l = 0, r = nums.size() - 1;
        int left = nums[l], right = nums[r];
        while(r>l){
            int mid = l + r >> 1;
            if(nums[mid] <= left && nums[mid] <= right) r = mid;
            else l = mid+1;
        }
        int pivot;
        if(nums[r]<nums[0]) pivot = r;
        else pivot = 0;
        
        if(pivot){
            l = 0, r = pivot-1;
            while(r>l){
                int mid = l + r >> 1;
                if(nums[mid] >= target) r = mid;
                else l = mid+1;
            }
            if(target == nums[r]) return r;
            l = pivot, r = nums.size()-1;
            while(r>l){
                int mid = l + r >> 1;
                if(nums[mid] >= target) r = mid;
                else l = mid+1;
            }
            if(target == nums[r]) return r;
            else return -1;
        } else {
            l = 0, r = nums.size()-1;
            while(r>l){
                int mid = l + r >> 1;
                if(nums[mid] >= target) r = mid;
                else l = mid+1;
            }
            if(target == nums[r]) return r;
            else return -1;
        }
    }
};
```

