# 问题 #
给定两个有序整数数组 nums1 和 nums2，将 nums2 合并到 nums1中，使得 num1 成为一个有序数组。
注意:
你可以假设 nums1有足够的空间（空间大小大于或等于m + n）来保存 nums2 中的元素。在 nums1 和 nums2 中初始化的元素的数量分别是 m 和 n。
# 代码 #
```	C
    void merge(int* nums1, int m, int* nums2, int n) {  
        int index = m + n - 1;  
        int i = m - 1;  
        int j = n - 1;  
        while (j >= 0){  
            if (i < 0) nums1[index--] = nums2[j--];  
            else nums1[index--] = nums1[i] > nums2[j] ? nums1[i--] : nums2[j--];  
        }  
    }  
```
# 总结 #
对数组1和2进行标号进行比较，这时候有两种情况：如果是第一个数组用完了，说明剩下的(最小的那些)全是数组2，把数组2填充进去就好了;如果是第二个数组用完了，说明剩下的全是数组1，不用填充了，他们已经在了。对于else中的含义：这是一个三目运算符，如果前者大，则num1[idex]=num1[i],随后i和index进行减一操作
