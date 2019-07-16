## 48 Rotate Image

### 自己

```c++
class Solution {
int n = 0;
public:
    void r(vector<vector<int>> &m, int ul, int rd){
        if(ul >= rd) return;
        for(int i = ul; i < rd; i++){
            swap(m[ul][i], m[i][rd]);
            swap(m[ul][i], m[rd][n-i]);
            swap(m[ul][i], m[n-i][ul]);
        }
        r(m, ul+1, rd-1);
    }
    
    void rotate(vector<vector<int>>& m) {
        if(m.empty()) return;
        n = m.size() - 1;
        r(m, 0, n);
        return;
    }
};
```

### 大雪菜

```c++
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
        int n = matrix.size();
        for (int i = 0; i < n; i ++ )
            for (int j = i + 1; j < n; j ++ )
                swap(matrix[i][j], matrix[j][i]);
        for (int i = 0; i < n; i ++ )
            for (int j = 0, k = n - 1;
                    j < k; j ++, k -- )
                swap(matrix[i][j], matrix[i][k]);
    }
};
```

