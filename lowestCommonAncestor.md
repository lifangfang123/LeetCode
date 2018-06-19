# 问题 #
给定一个二叉搜索树, 找到该树中两个指定节点的最近公共祖先。
# 代码 #
```C++

class Solution {
public:
    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
   while (root) {  
 if (root->val > p->val && root->val > q->val) {  
  root = root->left;  
 }  
 else if (root->val < p->val && root->val < q->val) {  
  root = root->right;  
 }  
 else {  
  return root;  
 }  
}  
return root;     
    }
};
```
# 总结 #
二叉搜索树的特点是节点大于左子树，小于右子树。 当二叉树同时大于左右子树时，可以知道root,p,q之间的关系：1、一个大于根节点一个小于根节点；2、两个都大于根节点（位于右子树）；3、两个都小于根节点（位于左子树）。