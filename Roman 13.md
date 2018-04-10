# 问题 #
给出一组罗马数字的字符串，将字符串转换成阿拉伯数字（输入的范围是1~3999）
# 代码 #
```C
int romanToInt(char s[]) {  
    int toNumber(char c){  
    switch(c){  
        case 'I':return 1;   
        case 'V':return 5;   
        case 'X':return 10;  
        case 'L':return 50;  
        case 'C':return 100;  
        case 'D':return 500;  
        case 'M':return 1000;  
    }  
    return 0;  
    }
   int len, i, ret=0;         
  
    len = strlen(s);                
    if(s == 0)  return 0;     
    ret = toNumber(s[len-1]);       
    for(i=len-1; i>0; i--){         
        if(toNumber(s[i-1]) >= toNumber(s[i]))   
            ret += toNumber(s[i-1]);  
        else  
            ret -= toNumber(s[i-1]);  
    }  
      
    return ret;        
}  
  
```
# 总结 #
罗马数字从右开始读，所以代码需要先读取字符串中最后一个字符，后再依次向前读取，直至所有字符读取完毕；每次提取的字符与上一次提取的字符进行比较，如果左边数字大于等于右边的，则相加若左边小于右边，则相减