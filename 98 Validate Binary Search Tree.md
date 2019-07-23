## 98 Validate Binary Search Tree

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
    bool iV(TreeNode *root, long max, long min) {
        if(!root) return true;
        if(root->val >= max || root->val <= min) return false;
        return iV(root->left, root->val, min) && iV(root->right, max, root->val);
    }
    
    bool isValidBST(TreeNode* root) {
        if(!root) return true;
        long max = LONG_MAX, min = LONG_MIN;
        return iV(root, max, min);
    }
};
```

