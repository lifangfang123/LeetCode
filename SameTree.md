# 问题 #
相同的树
给定两棵二叉树，写一个函数来检查他们是否相等
这里说的两棵二叉树相等是指他们结构完全相同并且对应的结点有相同的值
# 代码 #
```C
bool isSameTree(struct TreeNode* p, struct TreeNode* q) {
    if (p == NULL && q == NULL) return true;  
    if (p == NULL || q == NULL) return false;  
    if (p->val==q->val && isSameTree(p->left, q->left) && isSameTree(p->right, q->right))  
        return true;  
    else  
        return false;  
}  
```
# 总结 #
当比较两棵树的对应两个结点时，如果他们的左子树完全一样，右子树完全一样，同时这两个结点的值也一样，那么树是完全一样的了。第一个if是俩个都为空，第二个if是一个为空另一个不空,第三个是都不为空，俩个二叉树左右节点相等，则相同