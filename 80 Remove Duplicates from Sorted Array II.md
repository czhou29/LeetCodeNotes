## 80 Remove Duplicates from Sorted Array II

```c++
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        if(nums.size() <= 2) return nums.size();
        
        int i = 2;
        for(int j = 2; j < nums.size(); j++){
            if(nums[i-2] != nums[j]){
                nums[i++] = nums[j];
            }
        }
        return i;
    }
};
```

