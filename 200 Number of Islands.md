###  200 Number of Islands

```c++
class Solution {
public:
    int dx[4] = {0, 1, 0, -1};
    int dy[4] = {1, 0, -1, 0};
    
    void dfs(vector<vector<char>>& grid, int x, int y) {
        grid[x][y] = '0';
        for(int i = 0; i < 4; i++) {
            int tx = x + dx[i], ty = y + dy[i];
            if(tx >= 0 && tx < grid.size() && ty >= 0 && ty < grid[0].size() && grid[tx][ty] == '1')
                dfs(grid, tx, ty);
        }
    }
    
    int numIslands(vector<vector<char>>& grid) {
        if(grid.size() == 0) return 0;
        if(grid[0].size() == 0) return 0;
        int m = grid.size(), n = grid[0].size();
        int res = 0;
        for(int i = 0; i < m; i++) {
            for(int j = 0; j < n; j++){
                if(grid[i][j] == '1'){
                    res++;
                    dfs(grid, i, j);
                }
            }
        }
        return res;
    }
};
```

