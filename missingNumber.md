# 问题 #
给出一个包含 0, 1, 2, ..., n 中 n 个数的序列，找出 0 .. n 中没有出现在序列中的那个数。
# 代码 #
```C++
 class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int i=0;
        sort(nums.begin(),nums.end());
        while(nums[i]==i)
        {
         i++;   
        }
        return i;
    }
};

```

# 总结 #
先排序，将每个数字对应下标，通过一层循环判断是否与当前下标匹配.