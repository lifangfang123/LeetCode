# 问题 #
给定一个整数类型的数组 nums，请编写一个能够返回数组“中心索引”的方法。
我们是这样定义数组中心索引的：数组中心索引的左侧所有元素相加的和等于右侧所有元素相加的和。
如果数组不存在中心索引，那么我们应该返回 -1。如果数组有多个中心索引，那么我们应该返回最靠近左边的那一个。

# 代码 #
```C++
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int sum = accumulate(nums.begin(), nums.end(), 0);
        int curSum = 0, n = nums.size();
        for (int i = 0; i < n; ++i) {
            if (sum - nums[i] == 2 * curSum) return i;
            curSum += nums[i];
        }
        return -1;
    }
};
```
# 总结 #
直接按题意去搜索，因为中枢点可能出现的位置就是数组上的位置，所以搜索一遍就可以找出来，先求出数组的总和，然后维护一个当前数组之和curSum，然后对于遍历到的位置，用总和减去当前数字，看得到的结果是否是curSum的两倍，如果是，那么当前位置就是中枢点，返回即可；否则就将当前数字加到curSum中继续遍历，遍历结束后还没返回，说明没有中枢点，返回-1即可