# 问题 #
给定一个所有节点为非负值的二叉搜索树，求树中任意两节点的差的绝对值的最小值。
# 代码 #
```c++
class Solution {
public:
    int getMinimumDifference(TreeNode* root) {
        int res = INT_MAX, pre = -1;
        inorder(root, pre, res);
        return res;
    }
    void inorder(TreeNode* root, int& pre, int& res) {
        if (!root) return;
        inorder(root->left, pre, res);
        if (pre != -1) res = min(res, root->val - pre);
        pre = root->val;
        inorder(root->right, pre, res);
    }
};

```
# 总结 #
由于BST的左<根<右的性质可知，如果按照中序遍历会得到一个有序数组，那么最小绝对差肯定在相邻的两个节点值之间产生。所以我们的做法就是对BST进行中序遍历，然后当前节点值和之前节点值求绝对差并更新结果res。这里需要注意的就是在处理第一个节点值时，由于其没有前节点，所以不能求绝对差。这里我们用变量pre来表示前节点值，这里由于题目中说明了所以节点值不为负数，所以我们给pre初始化-1，这样我们就知道pre是否存在。