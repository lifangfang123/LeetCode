# 问题 #
给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现了三次。找出那个只出现了一次的元素。
# 代码 #
```C
int singleNumber(int* nums, int numsSize) {
 int singleNumber(int* nums, int numsSize) {
    if(numsSize == 1)
    {
        return nums[0];
    }
    while(numsSize != 1)
    {
        nums[0] ^= nums[numsSize - 1];
        numsSize--;
    }
    return nums[0];
}
    
```
# 总结 #
如果数组中只有一个数字，则返回的数字就是需要找到的数字；如果数组中多于四个数字，按照异或运算，nums[0] ^= nums[numsSize - 1]，这句代表，数组中的第一个数字和和后面的数字进行异或运算，然后返回到nums[0]，依次进行下去，异或运算，相同为1，不同为0。