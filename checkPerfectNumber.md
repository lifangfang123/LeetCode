# 问题 #
对于一个 正整数，如果它和除了它自身以外的所有正因子之和相等，我们称它为“完美数”。
给定一个 正整数 n， 如果他是完美数，返回 True，否则返回 False
# 代码 #
```C
class Solution {
public:
    bool checkPerfectNumber(int num) 
    {
        int res=1,i;
        if(num==1)
            return 0;
        for(i=2;i*i<=num;i++)
        {
            if(num%i==0)
                res=res+i+num/i;
            if(i*i==num) res=res-i;
        }
        if(res==num)
            return 1;
        else 
            return 0;
    }
};
```
# 总结 #
遍历的时候加上i与num/i这两个因子来防止超出时间限制，然后从2遍历到num的开方，最后比较和res与num是否相等。