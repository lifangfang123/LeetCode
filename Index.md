# 问题 #
在一个给定的数组nums中，总是存在一个最大元素 。
查找数组中的最大元素是否至少是数组中每个其他数字的两倍。
如果是，则返回最大元素的索引，否则返回-1。
# 代码 #
```C++
class Solution {
public:
    int dominantIndex(vector<int>& nums) {
        int mx = INT_MIN, secondMx = INT_MIN, mxId = 0;
        for (int i = 0; i < nums.size(); ++i) {
            if (nums[i] > mx) {
                secondMx = mx;
                mx = nums[i];
                mxId = i;
            } else if (nums[i] > secondMx) {
                secondMx = nums[i];
            }
        }
        return (mx - secondMx >= secondMx) ? mxId : -1;
    }
};

```
# 总结 #
首先明确的一点是这个要求的数字一定是数组中的最大数字，因为其是其他所有的数字的至少两倍。然后就是，如果该数字是数组中第二大的数字至少两倍的话，那么它一定是其他所有数字的至少两倍，所以我们可以遍历一次数组分别求出最大数字和第二大数字，然后判断一下最大数字是否是第二大数字的两倍即可，注意这里我们判断两倍的方法并不是直接相除，为了避免除以零的情况，我们采用减法