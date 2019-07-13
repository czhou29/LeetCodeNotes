## 278 First Bad Version

```c++
// Forward declaration of isBadVersion API.
bool isBadVersion(int version);

class Solution {
public:
    int firstBadVersion(int n) {
        if(n==0) return 1;
        unsigned int l = 0, r = n-1;
        while(r>l){
            int mid = l + 0ll + r >> 1;
            if(isBadVersion(mid+1)) r = mid;
            else l = mid + 1;
        }
        return r+1;
    }
};
```

