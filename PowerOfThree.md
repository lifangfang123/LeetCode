# 问题 #
给出一个整数，写一个函数来确定这个数是不是3的一个幂。
# 代码 #
```C
    bool isPowerOfThree(int n) {  
        if (n < 1) return false;  
        if (n == 1) return true;  
        while (n > 1){  
            if (n%3) return false;  
            n /= 3;  
        }  
        return true;  
    }  

```
# 总结 #
判断一个数是不是3的幂只需要不断地除以3即可，只要出现除不通的情况就判断为不是3的幂，如果能一直除到商为1，则它是3的幂。