## 104 Maximum Depth of Binary Tree

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
    int tv(TreeNode *t, int d) {
        if(!t) return d;
        return max(tv(t->left, d+1), tv(t->right, d+1));
    }
    
    int maxDepth(TreeNode* root) {
        int d = 0;
        if(!root) return d;
        return max(tv(root->left, d+1), tv(root->right, d+1));
    }
};
```

