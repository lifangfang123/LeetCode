# 问题 #
给一个长度为偶数的整数数组，数组中不同数字都代表不同糖果，将糖果平均分给弟弟和妹妹，妹妹最多能得到几种糖果。  
# 编程 #
```C
 class Solution {
public:
    int distributeCandies(vector<int>& candies) {
   if(candies.size()%2 != 0)
            return 0;
        unordered_map<int, int> HASH;
        int res = 0;
        for(int c: candies){
           HASH[c]++;
           if(HASH[c]==1 && res<candies.size()/2)
                res++;
        }
        return res;
  } 
     
};
      
```
# 总结 #
用hash表。定义unordered_map《int, int> HASH，定义一个整数res存储妹妹能得到糖果的种类 遍历数组，将每个数字存到对应位置中，如果存入后这个数字对应位置的数(该种糖果数量)等于1且res小于数组长度的一半，res++,最后返回res
