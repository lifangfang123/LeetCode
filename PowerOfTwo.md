# 问题 #
给定一个整数，写一个函数来判断它是否是2的幂。
# 代码 #
```C
bool isPowerOfTwo(int n) {
      if(n<=0)
        return false;
    if(n&(n-1))
        return false;
    return true;
}
```
# 总结 #
if是二进位数（n和n-1）按位取与运算来判断是否为2的幂。