## 110 Balanced Binary Tree

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
    bool isBalanced(TreeNode* root) {
        int h;
        return dfs(root, h);
    }
    
    bool dfs(TreeNode *t, int &h) {
        if(!t) {
            h = 0;
            return true;
        }
        
        int left, right;
        if(!dfs(t->left, left)) return false;
        if(!dfs(t->right, right)) return false;
        
        h = max(left, right) + 1;
        return abs(left-right) <= 1;
    }
};
```

