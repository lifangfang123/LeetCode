# 问题 #
给定一个数组 nums, 编写一个函数将所有 0 移动到它的末尾，同时保持非零元素的相对顺序。
# 代码 #
```C
void moveZeroes(int* nums, int numsSize) {
    int i=0, j=0;

    while(j<numsSize) 
    {  
        if(nums[j]!=0) 
        {  
            if(j!=i) 
            {   
                nums[i++] = nums[j];  
                nums[j] = 0;  
            } 
            else 
            {  
                ++i;  
            }  
        }   
        ++j;  
    } 
}
```
# 总结 #
利用双指针，i指向0的元素，j指向非0的元素，从头开始遍历，如果遇到i和j的位置不相等，则交换i和j的内容，并将j的内容置为0。