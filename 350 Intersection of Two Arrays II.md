## 350 Intersection of Two Arrays II

```c++
class Solution {
public:
    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
        multiset<int> s1(nums1.begin(), nums1.end()), s2(nums2.begin(), nums2.end());
        multiset<int> res;
        set_intersection(s1.begin(), s1.end(), s2.begin(), s2.end(), inserter(res, res.begin()));
        return vector<int>(res.begin(), res.end());
    }
};
```

