# 问题 #
实现 strStr() 函数。 给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回 -1。
# 代码 #
```C
class Solution {
public:
    int strStr(string haystack, string needle)
    {
        int i,j,a,b;
        a=haystack.size();
        b=needle.size();
        if (needle.empty()) 
            return 0;      
        if (a<b) 
            return -1;
        for (i=0;i<=a-b;i++) 
        {
            for(j=0;j<b;j++) 
            {
                if(haystack[i+j]!=needle[j]) 
                    break;
            }
            if(j==b) 
                return i;
        }
        return -1;
    }
};
```
# 总结 #
首先判断needle是否0，如果是0时，返回0。如果needle的长度大于haystack的时候，就返回-1。 对于needle每一个字符都要遍历一遍字符串，比较当不同的时候跳出循环。如果最后j与needle长度相同，则说明长字符串中含有短的，则返回初始坐标。