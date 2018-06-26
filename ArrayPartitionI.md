# 问题 #
给定长度为 2n 的数组, 你的任务是将这些数分成 n 对, 例如 (a1, b1), (a2, b2), ..., (an, bn) ，使得从1 到 n 的 min(ai, bi) 总和最大。
# 代码 #
```C++


class Solution {
public:
    int arrayPairSum(vector<int>& nums) {
     int res = 0, n = nums.size();
        sort(nums.begin(), nums.end());
        for (int i = 0; i < n; i += 2) {
            res += nums[i];
        }
        return res;
    }
};
```

# 总结 #
在数组中找到使di（ai和bi之间的距离）的和尽可能小的对。显然，相邻元素的这些距离之和是最小的。