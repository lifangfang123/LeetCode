# 问题 #
请编写一个函数，其功能是将输入的字符串反转过来。
# 代码 #
```C
class Solution {
public:
    string reverseString(string s) {
 int i=0;
 int j=s.size()-1;
 for(i,j;j>i;i++,j--){
   swap(s[i],s[j]);
 }  
 return s; 
}
};  

```
# 总结  #
用到了几个函数
1. string里面的size（）用于获取字符串字节数（带字符串尾‘\0’的长度）2. swap()函数，用于交换两个变量的值