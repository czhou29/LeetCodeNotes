##  240 Search a 2D Matrix II

```c++
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int m = matrix.size();
        if(m == 0) return false;
        int n = matrix[0].size();
        if(n == 0) return false;
        int up = 0, right = n-1;
        while(up < m && right >= 0) {
            if(matrix[up][right] == target) return true;
            else if (matrix[up][right] < target) up++;
            else right--;
        }
        return false;
    }
};
```

