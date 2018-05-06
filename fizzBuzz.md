# 问题 #
给定一个数n，要求写出代表1到n的字符串，其中能被3整除的输出 “Fizz”，能被5整除的输出 “Buzz”，同时被3和5整除的输出 “FizzBuzz”。
# 代码 #
class Solution {
public:
    vector<string> fizzBuzz(int n) {
        vector<string> s;
        for(int i=1;i<=n;i++)
           {
               if(i%15==0)
                s.push_back("FizzBuzz");
               else if(i%3==0)
                s.push_back("Fizz");
               else if(i%5==0)
                s.push_back("Buzz");
               else
                s.push_back(to_string(i));
           }
        return s;
    }
# 总结 #
学习两点一个是C++中vector的应用，另一个是C++中int转string的方法。(1)利用stringstream(2)利用sprintf int->char[](3)利用itoa int->char[]4)利用to_string 