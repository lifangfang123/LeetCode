# 问题 #
翻转一个32位的有符号整数，溢出的时候返回0
# 代码 #
```C
int reverse(int x) {
    int temp=0;  
  
    while(0 != x){  
          
        if (temp > 2147483648/10 || temp <-2147483648 /10){     
             return 0;  
        }  
       temp = temp*10 + x % 10;        
        x = x / 10;
   }
   return temp;  
}  
```
# 总结 #
判断有符号数的范围，主要利用对输入的x不断进行以10为除数的取余和整除操作。