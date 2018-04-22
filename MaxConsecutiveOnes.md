# 问题 #
给定一个二进制数组， 计算其中最大连续1的个数
注意： 输入的数组只包含 0 和1。输入数组的长度是正整数，且不超过 10,000。

# 代码 #
```C
int findMaxConsecutiveOnes(int* nums, int numsSize) {
    int i=0,count=0,k=0,max=0;
    for(i=0;i<numsSize;i++)
    {
        if(nums[i]==1)
        {
            count++;
        }
        else
        {
            if(count>max)
                max=count;
            count=0;
        }
    }
    if(count>max) 
        max=count;
    return max;
} 
```
# 总结 #
先判断nums[i]是不是为零，如果为零，count 加1，count保存的是1的个数，max是连续是一的最大值。