You are given a binary tree. Find the maximum depth from the given binary tree. 


### Solution 
```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */

class Solution {
public:
   public:
    int getMaxDepth(TreeNode* root, int depth){
        
       // cout<<depth<<endl;
        
        if(root==nullptr){
            return depth;
        }
        
        int leftDepth = getMaxDepth(root->left, depth+1);
        int rightDepth = getMaxDepth(root->right, depth+1);
        
        return max(leftDepth, rightDepth);
    }
    
    int maxDepth(TreeNode* root) {
        
        return  getMaxDepth(root,0);
    }

};

```
