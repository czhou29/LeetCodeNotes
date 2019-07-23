## 102 Binary Tree Level Order Traversal

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
    vector<int> get_val(vector<TreeNode *> &level) {
        vector<int> res;
        for(auto &i: level) {
            res.push_back(i->val);
        }
        return res;
    }
    
    vector<vector<int>> levelOrder(TreeNode* root) {
        vector<vector<int>> res;
        if(!root) return res;
        vector<TreeNode *> level;
        level.push_back(root);
        res.push_back(get_val(level));
        while(true) {
            vector<TreeNode *> newLevel;
            for(auto &t: level) {
                if(t->left) newLevel.push_back(t->left);
                if(t->right) newLevel.push_back(t->right);
            }
            if(newLevel.size() != 0) {
                level = newLevel;
                res.push_back(get_val(newLevel));
            } else break;
        }
        return res;
    }
};
```

