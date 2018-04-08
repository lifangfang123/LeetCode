# 问题 #
    给出一个数列，找出和为目标值的两个数。
# 编程 #
```C
    int* twoSum(int* nums, int numsSize, int target) {
    int *a = (int*)malloc(2*sizeof(int));  
    for(int i = 0;i<numsSize;i++)  
    {  
        for(int j = i+1;(j<numsSize && j != i);j++)  
        {  
            if(nums[i] + nums[j] == target)  
            {  
                a[0] = i;  
                a[1] = j;  
            }  
        }  
    }  
    return a;  
}  
```
# 总结 #
    利用循环，把两个数相加的和与目标值进行比较。