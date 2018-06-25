# 问题 #
给定一个整数数组 nums，求出数组从索引 i 到 j (i ≤ j) 范围内元素的总和，包含 i, j 两点。
# 代码 #
```C++

class NumArray {   
    private: vector<int> nums;  
public:  
    NumArray(vector<int> nums) {
     this->nums=nums;  
        
    }
    
    public:int sumRange(int i, int j) {
        int sum1;
          sum1=0;
          for(int k=i;k<=j;k++){
              sum1=sum1+nums[k];   
          }
        return sum1;
    }
  
};
```
# 总结 #
找到数组长度对应为i的数值，依次累加到长度为j的数值，返回总和。