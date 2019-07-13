## 349 Intersection of Two Arrays

```c++
class Solution {
public:
    vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
        set<int> nums1s(nums1.begin(), nums1.end()), nums2s(nums2.begin(), nums2.end()),ress;
        set_intersection(nums1s.begin(), nums1s.end(), nums2s.begin(), nums2s.end(), inserter(ress, ress.begin()));
        return vector<int>(ress.begin(), ress.end());
    }
};
```

