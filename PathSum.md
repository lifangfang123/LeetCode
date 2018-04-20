# 问题 #
给定一棵二叉树和一个总和，确定该树中是否存在根到叶的路径，这条路径的所有值相加等于给定的总和。
# 代码 #
bool hasPathSum(struct TreeNode* root, int sum) {
   if (!root) return false;  
    if (!root->left && !root->right) return root->val == sum;  
    bool flagl = false, flagr = false;  
    if (root->left) flagl = hasPathSum(root->left, sum - root->val);  
    if (root->right) flagr = hasPathSum(root->right, sum - root->val);  
    return flagl || flagr;   
}
# 总结 #
if（！root->left&&!root->right)是root->left并且root->right都为假的时候执行语句。采用前序遍历，从根节点到左子树（或右子树）进行寻找。