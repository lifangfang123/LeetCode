# 问题 #
用[a1,a2,...,an]表示一支股票在n个时刻的价格，问如何买卖股票可以使得收益最大。
# 代码 #
```C
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        if (prices.size() == 0) return 0;
        int buy_in = prices[0], sum = 0;
        for (int i = 1; i < prices.size(); ++i) {
            if (prices[i] > buy_in) {
                sum += prices[i] - buy_in;
                buy_in = prices[i];
            } else {
                buy_in = prices[i];
            }
        }
        return sum;
    }
};
```
# 总结 #
第一个元素开始遍历至最后一个元素；
若下一个元素比当前元素大，那么就抛售；并以下一个元素的价钱买入，同时累加利润；
若下一个元素比当前元素小，那么就以下一个元素的价钱买入（若连续出现递减的情况，那么最后的买入价格是最后那个最小的元素