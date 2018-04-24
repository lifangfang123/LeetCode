# 问题 #
判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。
# 代码 #
```C
bool isPalindrome(int x) {
    int a=0,b=abs(x),flag;
    if (x<0)
         flag=0;
    else{
        while(b)
        {
            if (abs(a) > INT_MAX / 10) 
                 flag=0;
            a=a*10+b%10;
            b=b/10;
        }
    if (a==x)
         flag=1;
   } 
    if (flag==0)
        return false;
    if(flag==1)
        return true;
    return flag;
}
```
# 总结 #
if (abs(a) > INT_MAX / 10) 表示所输出的颠倒之后的数不能超过32位。回文数是指正序和倒序是都是一样的数。如果为负数肯定不是回文数；如果是非负数将整数颠倒，在判断颠倒之后的数与原来的整数是否相等，相等则为回文数。