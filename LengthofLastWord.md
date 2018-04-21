# 问题 #
给定一个仅包含大小写字母和空格 ' ' 的字符串，返回其最后一个单词的长度。
如果不存在最后一个单词，请返回 0 。
说明：一个单词是指由字母组成，但不包含任何空格的字符串。
# 代码 #
```C
int lengthOfLastWord(char* s) {
   int i,count=0;
   int len=strlen(s); 
   int left=0; int right=len-1; 
   while(s[left]==' ') 
       left++; 
   while(s[right]==' ')
       right--; 
    for(i=right;i>=left;i--) 
    { if(s[i]!=' ') 
        count++; 
      if(s[i]==' ') 
          break; 
    } 
    return count; 
    
}
```
# 总结 #
首先去除首尾的空格（两个while），单词与单词的分隔是以空格划分的，所以，for中遇到空格就跳出循环，并且返回对应的单词长度（count）。