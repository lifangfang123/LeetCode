# 问题 #
给定一个整数 (32位有符整数型)，请写出一个函数来检验它是否是4的幂。
# 代码 #
```c
bool isPowerOfFour(int num) {
   if(num<=0) return false;
        else return ((num&(num-1))==0)&&((num&0x55555555)==num);
    }

```
# 总结 #
num&(num-1))==0先判断是不是2的幂，在利用num&0x55555555==num，两个结合来判断是不是四的幂。num&0x55555555这句的意思是保留0，2，4，，6，8等偶数位上的1。