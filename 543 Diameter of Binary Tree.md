## 543 Diameter of Binary Tree

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
    int dB(TreeNode *t, int &ans) {
        if(!t) return -1;
        int d1 = dB(t->left, ans), d2 = dB(t->right, ans);
        ans = max(ans, d1+d2+2);
        return max(d1, d2)+1;
    }
    
    int diameterOfBinaryTree(TreeNode* root) {
        if(!root) return 0;
        int ans = 0;
        dB(root, ans);
        return ans;
    }
};
```



