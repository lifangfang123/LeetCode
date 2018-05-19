# 问题 #
给定一个整数数组，判断是否存在重复元素。

如果任何值在数组中出现至少两次，函数返回 true。如果数组中每个元素都不相同，则返回 false。
# 代码 #
class Solution {  
public:  
    bool containsDuplicate(vector<int>& nums) {  
        return set<int>(nums.begin(),nums.end()).size() < nums.size();  
    }  
};  
# 总结 #
set容器，要学习set容器原理