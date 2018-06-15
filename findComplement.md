# 问题 #
给定一个正整数，输出它的补数。补数是对该数的二进制表示取反。

注意:

给定的整数保证在32位带符号整数的范围内。
你可以假定二进制数不包含前导零位。
# 代码 #
```C++
 class Solution {
public:
    int findComplement(int num) 
    {
        int i;
        bool start=false;
        for (i=31;i>=0;i--)
        {
            if(num&(1<<i)) 
                start=true;
            if(start)
                num=num^(1<<i);
        }
        return num;
    }
};
```

# 总结 #
按照从高往低的顺序遍历，因为起始位置从最高位的1开始的，前面的0是不能被翻转的，遍历时如果遇到第一个1了后，我们的flag就赋值为true，然后翻转了，翻转的方法就是对应位异或一个1