## 51 N-Queens

```c++
class Solution {
public:
    int n;
    vector<bool> col, dg, udg;
    vector<string> q;
    vector<vector<string>> res;
    
    void dfs(int u){
        if(u == n) {
            res.push_back(q);
            return;
        }
        
        for(int i = 0; i < n; i++) {
            if(!col[i] && !dg[u+i] && !udg[n-u+i]){
                col[i] = dg[u+i] = udg[n-u+i] = true;
                q[u][i] = 'Q';
                dfs(u+1);
                q[u][i] = '.';
                col[i] = dg[u+i] = udg[n-u+i] = false;
            }
        }
    }
    
    vector<vector<string>> solveNQueens(int x) {
        n = x;
        col = vector<bool>(n, false);
        dg = vector<bool>(2*n, false);
        udg = vector<bool>(2*n, false);
        q = vector<string>(n, string(n, '.'));
        dfs(0);
        return res;
    }
};
```

