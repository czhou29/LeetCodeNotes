## 94 Binary Tree Inorder Traversal

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
    void iT(TreeNode *t, vector<int> &res) {
        if(!t) return;
        iT(t->left, res);
        res.push_back(t->val);
        iT(t->right, res);
    }
    
    vector<int> inorderTraversal(TreeNode* root) {
        vector<int> res;
        if(!root) return res;
        
        iT(root->left, res);
        res.push_back(root->val);
        iT(root->right, res);
        
        return res;
    }
};
```

