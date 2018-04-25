# 问题 #
给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。
# 代码 #
```C
int firstUniqChar(char* s) {
    int hashtable[256];
    int i,l=strlen(s),ret=-1;
    memset(hashtable,0,sizeof(int)*256);
    if(l){
        for(i=0;i<l;i++)
        {
            hashtable[s[i]]++;
        }
        for(i=0;i<l;i++)
        {
            if(hashtable[s[i]]==1)
            {
                ret=i;
                break;
            }
        }
    }
    return ret;
}
```
# 总结 #
一个字符串容纳256个元素，新建一个数组并初始化，memset() 函数常用于内存空间初始化，首先遍历一次字符串，确定每个字符出现的次数，然后再遍历字符串，找出第一个只出现一次的字符。