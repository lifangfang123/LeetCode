# 问题 #
给定一个二进制矩阵 A，我们想先水平翻转图像，然后反转图像并返回结果。

水平翻转图片就是将图片的每一行都进行翻转，即逆序。例如，水平翻转 [1, 1, 0] 的结果是 [0, 1, 1]。

反转图片的意思是图片中的 0 全部被 1 替换， 1 全部被 0 替换。例如，反转 [0, 1, 1] 的结果是 [1, 0, 0]。
# 代码 #
```C++
class Solution {
 public:

vector<vector<int>> flipAndInvertImage(vector<vector<int>>& A) 
{
    for (int i=0; i<A.size(); i++)  
    {  
        reverse(A[i].begin(),A[i].end());  
        for (int j=0;j<A[i].size();j++)  
        {  
            A[i][j]=！A[i][j];  
        }  
    }  
    return A;  
    
}
};
```

# 总结 #
利用双重循环，先利用reverse函数对每一行元素进行水平翻转，载对每一个元素取反即可