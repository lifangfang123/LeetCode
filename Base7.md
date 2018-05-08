# 问题 #
给定一个整数，将其转化为7进制，并以字符串形式输出。

# 代码 #
class Solution {
public:
    string convertToBase7(int num) {
        if (num==0) 
            return "0";
        bool flag = (num>0)?true:false;
        num = (num>0)?num:num*(-1);
        string res;
        int tmp;
        while (num!=0)
        {
            tmp = num%7;
            num /= 7;
            res =  to_string(tmp)+res;
        }
        if (!flag)
            res = string(1, '-')+res;
        return res;
    }
};
# 总结 #
1. 字符串初始化。2.字符串的连接。3.to_string: convert numerical value to string