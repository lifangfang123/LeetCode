# 问题 #
给定一个字符串来代表一个学生的出勤纪录，这个纪录仅包含以下三个字符：

    'A' : Absent，缺勤
    'L' : Late，迟到
    'P' : Present，到场

如果一个学生的出勤纪录中不超过一个'A'(缺勤)并且不超过两个连续的'L'(迟到),那么这个学生会被奖赏。
你需要根据这个学生的出勤纪录判断他是否会被奖赏。
# 代码 #
```C++
class Solution {
public:
    bool checkRecord(string s) 
    {
        int counta=0,countl=0;
        int s1=s.size();
        for(int i=0;i<s1;i++)
        {
            if(s[i]=='A')
            {
                counta++;
                if(counta>1)
                    return false;
            }
            else if(s[i+2]=='L'&&s[i+1]=='L'&&s[i]=='L')
            {
                if(i+2<s1)
                    return false;
            }
        }
        return true;
    }
};

```
# 总结 #
关于A的，很容易，遍历一遍字符串统计A出现次数，当次数大于1时，返回false，结束遍历。关于L的，也不难，遍历一遍字符串，当碰到L时，判断下一个字符和再下一个字符是否均为L，如果满足，返回false，结束遍历（这里要注意边界条件，即下一个字符是否在字符串以内）；如果不满足，那么继续处理下一个字符。