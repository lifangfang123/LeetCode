# 问题 #
 给定一个整数 n，返回 n! 结果尾数中零的数量。
# 编程 #
```C++
   class Solution {
public:
   int trailingZeroes(int n) {
        if(n<5) return 0;
        int count = 0;
        while(n/5 !=0){
            n/=5;
            count +=n;
        }
        return count;
    }
};
```
# 总结 #
 利用while循环和if条件语句。
