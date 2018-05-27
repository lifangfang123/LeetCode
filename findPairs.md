# 问题 #
给定一个整数数组和一个整数 k, 你需要在数组里找到不同的 k-diff 数对。这里将 k-diff 数对定义为一个整数对 (i, j), 其中 i 和 j 都是数组中的数字，且两数之差的绝对值是 k.
# 代码 #
```c++
class Solution {
public:
    int findPairs(vector<int>& nums, int k) {
        int res = 0, n = nums.size();
        unordered_map<int, int> m;
        for (int num : nums) ++m[num];
        for (auto a : m) {
            if (k == 0 && a.second > 1) ++res;
            if (k > 0 && m.count(a.first + k)) ++res;
        }
        return res;
    }
};
```
# 总结 #
由于k有可能为0，而只有含有至少两个相同的数字才能形成数对，那么就是说我们需要统计数组中每个数字的个数。我们可以建立每个数字和其出现次数之间的映射，然后遍历哈希表中的数字，如果k为0且该数字出现的次数大于1，则结果res自增1；如果k不为0，且用当前数字加上k后得到的新数字也在数组中存在，则结果res自增1。