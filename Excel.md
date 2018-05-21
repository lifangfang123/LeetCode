# 问题 #
给定一个正整数，返回它在 Excel 表中相对应的列名称。
# 代码 #
```C++
   class Solution {
public:
    string convertToTitle(int n) {
        string ret = "";
        while(n)
        {
            ret = (char)((n-1)%26+'A') + ret;
            n = (n-1)/26;
        }
        return ret;
    }
};  
```
# 总结 #
Excel序是这样的：A~Z, AA~ZZ, AAA~ZZZ, ……

本质上就是将一个10进制数转换为一个26进制的数

注意：由于下标从1开始而不是从0开始，因此要减一操作。