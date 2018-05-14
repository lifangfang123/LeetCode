# 问题 #
编写一个程序来检查给定的数字是否是一个丑陋的数字。丑陋的数字是正数，其主要因素仅包括2,3,5。
# 代码 #
class Solution {
public:
    bool isUgly(int num) {
          if(num == 0)
              return false;
          else if(num == 1)
              return true;
         else
         {
             while(num % 2 == 0)
                 num /= 2;
             while(num % 3 == 0)
                 num /= 3;
     while(num % 5 == 0)
                num /= 5;
 
            if(num == 1)
                 return true;
               else
                return false;
    }
}
};
# 总结 #
如果一个数被2、3、5除完之后是为1，则是丑数。