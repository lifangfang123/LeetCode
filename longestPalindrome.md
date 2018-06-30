# 问题 #
给定一个字符串 s，找到 s 中最长的回文子串。你可以假设 s 的最大长度为1000。
# 代码 #
int getlen(char *s, int a, int b, int len);
char* longestPalindrome(char* s);

int getlen(char *s, int a, int b, int len){
    int max = 0;
    for (; a>=0&&b<len; a--,b++){
        if (s[a] == s[b])  max+=2;
        else  break;
    }
    return max;
}

char* longestPalindrome(char* s)
{
    int len = strlen(s);
    int i,cur=0,temp,maxlen=1,index,maxindex=0;
    char *longeststr = NULL;

    if (len == 1)  return s;
    if (len==2 && s[0] == s[1])  return s;

    for (i=1; i<len-1; i++){
        if (s[i-1] == s[i]){
        cur = getlen(s, i-1, i, len);
            if (s[i] == s[i+1]){
                int temp = 1+getlen(s, i-1, i+1, len);
                cur = temp>cur?temp:cur;
            }
            index = i-(cur/2);
        }
        else if(s[i] == s[i+1]){
            cur = getlen(s, i, i+1, len);
            index = i-(cur/2)+1;
        }
        else if (s[i-1] == s[i+1]){
           cur = 1 + getlen(s, i-1, i+1, len);
           index = i-(cur/2);
        }

        if (cur > maxlen){
            maxlen = cur;
            maxindex = index;
        }
    }
    if (maxlen > 0){
        longeststr = (char *)calloc(maxlen+1, 1);
        memcpy(longeststr, s+maxindex, maxlen);
    }
    return longeststr;
}
# 总结 #
掌握回文字符的判断方法，返回字符串。