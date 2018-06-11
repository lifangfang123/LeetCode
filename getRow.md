# 问题 #
给定一个非负索引 k，其中 k ≤ 33，返回杨辉三角的第 k 行。
# 代码 #
```C++
class Solution {
public:
    vector<int> getRow(int rowIndex) {
vector<int> result(rowIndex+1,1);
        if(rowIndex<2)
           return result;
        for(int i=2;i<=rowIndex;i++){
            for(int j=i-1;j>0;j--){
                result[j]+=result[j-1];
            }
        }
        return result;   
    }
};
```
# 总结 #
根据杨辉三角的构成方式，每一行的元素等于上一行元素的左右两个数之和，然后将每一行都算出来，利用循环计算。 
