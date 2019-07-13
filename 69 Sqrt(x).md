## 69 Sqrt(x)

```c++
class Solution {
public:
    int mySqrt(int x) {
        double l = 0, r = x;
        while(r-l>1e-7){
            double mid = (l+r)/2;
            if(mid*mid>=x) r = mid;
            else l = mid;
        }
        return (int)r;
    }
};
```

```c++
class Solution {
public:
    int mySqrt(int x) {
        int l = 0, r = x;
        while (l < r)
        {
            int mid = (l + 1ll + r) / 2;
            if (mid <= x / mid) l = mid;
            else r = mid - 1;
        }
        return l;
    }
};
```

