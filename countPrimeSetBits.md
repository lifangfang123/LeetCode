# 问题 #
给定两个整数 L 和 R ，找到闭区间 [L, R] 范围内，计算置位位数为质数的整数个数。

（注意，计算置位代表二进制表示中1的个数。例如 21 的二进制表示 10101 有 3 个计算置位。还有，1 不是质数。）
# 代码 #
```C++
class Solution {
public:
    int countPrimeSetBits(int L, int R) {
        int res = 0;
        for (int i = L; i <= R; ++i) {
            int cnt = __builtin_popcount(i);
            res += cnt < 4 ? cnt > 1 : (cnt % 2 && cnt % 3);
        }
        return res;
    }
};

````
# 总结 #
直接使用了C++的内置函数__builtin_popcount来快速的求出非零位的个数cnt，然后又利用到了20以内的数，只要不能被2和3的一定是质数，又可以快速判断了质数了