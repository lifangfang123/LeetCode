# 问题 #
给定一个长度为 n 的整数数组 A 。

假设 Bk 是数组 A 顺时针旋转 k 个位置后的数组，我们定义 A 的“旋转函数” F 为：

F(k) = 0 * Bk[0] + 1 * Bk[1] + ... + (n-1) * Bk[n-1]。

计算F(0), F(1), ..., F(n-1)中的最大值。

# 代码 #
```C++
class Solution {
public:
    int maxRotateFunction(vector<int>& A) {
        int t = 0, sum = 0, n = A.size();
        for (int i = 0; i < n; ++i) {
            sum += A[i];
            t += i * A[i];
        }
        int res = t;
        for (int i = 1; i < n; ++i) {
            t = t + sum - n * A[n - i];
            res = max(res, t);
        }
        return res;
    }
};
```

# 总结 #
这个题最重要的是找规律，为了找规律，先把具体的数字抽象为A,B,C,D：

F(0) = 0A + 1B + 2C +3D

F(1) = 0D + 1A + 2B +3C

F(2) = 0C + 1D + 2A +3B

F(3) = 0B + 1C + 2D +3A

那么，通过仔细观察，可以得出下面的规律：

F(1) = F(0) + sum - 4D

F(2) = F(1) + sum - 4C

F(3) = F(2) + sum - 4B

规律为, F(i) = F(i-1) + sum - n*A[n-i]。