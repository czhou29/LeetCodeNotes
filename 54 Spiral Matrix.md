## 54 Spiral Matrix

```c++
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int>>& mt) {
        if(mt.empty()) return vector<int>{};
        vector<int> res;
        int m = mt.size(), n = mt[0].size();
        int dx[4] = {0, 1, 0, -1}, dy[4] = {1, 0, -1, 0};
        bool seen[m][n];
        memset(seen, false, sizeof seen);
        int k = 0;
        int x = 0, y = 0;
        for(int i = 0; i < m*n; i++){
            res.push_back(mt[x][y]);
            seen[x][y] = true;
            int cx = x + dx[k];
            int cy = y + dy[k];
            if(0<=cx && cx<m && 0<=cy&&cy<n&&!seen[cx][cy]){
                x = cx;
                y = cy;
            } else {
                k = (k+1)%4;
                x += dx[k];
                y += dy[k];
            }
        }
        return res;
    }
};
```

