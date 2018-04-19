# 问题 #
给定一个二叉树，找出其最大深度。
二叉树的深度为根节点到最远叶节点的最长路径上的节点数。
# 代码 #
```C
int maxDepth(struct TreeNode* root) {
  if (root == NULL) return 0;  
    int leftDepth = maxDepth(root->left);  
    int rightDepth = maxDepth(root->right);  
    if (leftDepth > rightDepth) return leftDepth + 1;  
    else return rightDepth + 1;  
} 
```    
# 总结 #
调用函数自身来得到左子树的最大深度和右子树的最大深度，将两个深度比较，取大者加1后返回。递归的终点是判断root是否为NULL，表示已到叶结点的左右子树上，此时返回深度为0。整个过程是递归式的深度优先遍历。