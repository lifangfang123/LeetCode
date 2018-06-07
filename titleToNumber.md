# 问题 #
给定一个Excel表格中的列名称，返回其相应的列序号。
# 代码 #
```C++
class Solution {
public:
    int titleToNumber(string s) {
      int res=0;
       for(int i=0;i<s.size();++i)
        {
            res=res*26+(s[i]-'A'+1);
        
        }
        return res;     
    }
}; 
}  
```
# 总结 #
26进制转10进制，列名称第一位代表列序号除以26的商，第二位代表余数。