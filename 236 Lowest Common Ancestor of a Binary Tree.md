## 236 Lowest Common Ancestor of a Binary Tree

```c++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    bool dfs(TreeNode *t, TreeNode *des, vector<TreeNode *> &path) {
        if(!t) return false;
        if(t == des || dfs(t->left, des, path) || dfs(t->right, des, path)) {
            path.push_back(t);
            return true;
        }
        return false;
    }
    
    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
        vector<TreeNode *> path_p, path_q;
        dfs(root, p, path_p), dfs(root, q, path_q);
        reverse(path_p.begin(), path_p.end()), reverse(path_q.begin(), path_q.end());
        int n = path_p.size() < path_q.size() ? path_p.size() : path_q.size();
        
        for(int i = n-1; i >= 0; i--)
            if(path_q[i] == path_p[i])
                return path_q[i];
        
        return root;
    }
};
```

