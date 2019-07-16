## 130 Surrounded Regions

```c++
class Solution {
int m, n;
int dr[4][2] = {{0, 1}, {1, 0}, {0, -1}, {-1, 0}};
vector<vector<bool>> bj;
public:
    void dfs(int x, int y, vector<vector<char>>& b){
        bj[x][y] = true;
        for(int i = 0; i < 4; i++){
            int cx = x + dr[i][0];
            int cy = y + dr[i][1];
            if(0<=cx && cx <m && 0<=cy && cy <n && !bj[cx][cy] && b[cx][cy] == 'O')
                dfs(cx, cy, b);
        }
    }
    
    void solve(vector<vector<char>>& b) {
        if(b.empty()) return;
        m = b.size(), n = b[0].size();
        bj = vector<vector<bool>>(m, vector<bool>(n, false));
        for(int j = 0; j < n; j++){
            if(b[0][j] == 'O')
                dfs(0, j, b);
            if(b[m-1][j] == 'O')
                dfs(m-1, j, b);
        }
        
        for(int i = 1; i < m-1; i++){
            if(b[i][0] == 'O')
                dfs(i, 0, b);
            if(b[i][n-1] == 'O')
                dfs(i, n-1, b);
        }
        for(int i = 0; i < m; i++)
            for(int j = 0; j < n; j++)
                if(!bj[i][j]) b[i][j] = 'X';
        return;
    }
};
```

