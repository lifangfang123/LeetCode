# 问题 #
编写一个函数来查找字符串数组中最长的公共前缀字符串。
# 代码 #
```C++
  class Solution {
public:
   string longestCommonPrefix(vector<string>& strs) { 
      int i,j;
        if(strs.size() == 0) return "";  
        if(strs.size() == 1) return strs[0];  
        for(i = 0; i< strs[0].length(); i++)  
            for(j = 1; j < strs.size(); j++)  
                if(i>= strs[i].length() || strs[i][j] != strs[0][j])  
                    return strs[0].substr(0,i);   
        return strs[0];   
    }       
    };
```
# 总结 #
将字符串数组中的第一个字符串为基准，遍历其它字符串，逐个字符查找