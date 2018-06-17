# 问题 #
在MATLAB中，有一个非常有用的函数 reshape，它可以将一个矩阵重塑为另一个大小不同的新矩阵，但保留其原始数据。

给出一个由二维数组表示的矩阵，以及两个正整数r和c，分别表示想要的重构的矩阵的行数和列数。

重构后的矩阵需要将原始矩阵的所有元素以相同的行遍历顺序填充。

如果具有给定参数的reshape操作是可行且合理的，则输出新的重塑矩阵；否则，输出原始矩阵。
# 代码 #
```C++
 class Solution {
public:
    vector<vector<int>> matrixReshape(vector<vector<int>>& nums, int r, int c) {
    
        //原矩阵的行，列
        int origin_r = nums.size();
        int origin_c = nums[0].size();
        int n = origin_c*origin_r;//元素个数
        if (n == r*c) {
            //新矩阵
            vector<vector<int>> newMaxtrix(r, vector<int>(c, 0));
            for (int i = 0; i < n; i++)
                newMaxtrix[i / c][i%c] = nums[i / origin_c][i%origin_c];
            return newMaxtrix;
        }
        else
            return nums;
        }
    
};
```

# 总结 #
1）origin_r * origin_c 的矩阵 reshape为 r*c的矩阵，需要满足：
origin_r * origin_c=r*c
（2）元素位置对应的关系
如果将矩阵横向展开为一维数组，元素个数为n=origin_r * origin_c
在元素在一维数组中对应的位置i：
原矩阵位置[i/origin_c,i%origin_c]
新矩阵位置[i/c,i%c] 