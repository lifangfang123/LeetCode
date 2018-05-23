# 问题 #
编写一个算法来判断一个数是不是“快乐数”。
一个“快乐数”定义为：对于一个正整数，每一次将该数替换为它每个位置上的数字的平方和，然后重复这个过程直到这个数变为 1，也可能是无限循环但始终变不到 1。如果可以变为 1，那么这个数就是快乐数。
# 代码 #
```C++
class Solution {
public:
    bool isHappy(int n) {
       int m = 0;

        if(n == 1 || n == 7) {
            return true;
        }
        if(n < 10) {
            return false;
        }
        while(n > 0) {
            m += (n % 10) * (n % 10);
            n = n/10;
        }
        return isHappy(m);
    }
};
```
# 总结 #
使用递归的思想，1和7单独进行处理。