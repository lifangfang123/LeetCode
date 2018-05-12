# 问题 #
自除数 是指可以被它包含的每一位数除尽的数。

例如，128 是一个自除数，因为 128 % 1 == 0，128 % 2 == 0，128 % 8 == 0。

还有，自除数不允许包含 0 。

给定上边界和下边界数字，输出一个列表，列表的元素是边界（含边界）内所有的自除数。
# 代码 #

class Solution {
public:
    vector<int> selfDividingNumbers(int left, int right) {
        vector<int> v;
        for (int i = left; i <= right; i++) {
            stringstream ss;
            ss << i; 
            string s = ss.str();
            int l = s.length(), t = 0;
            for (int j = 0; j < l; j++) {
                if (s[j] == '0') break;
                if (i % (s[j]-'0') == 0)
                    t++;
            }
            if (l == t) v.push_back(i);
        }
        return v;
    }
};

# 总结 #
找到所给边界之内的自分数self-dividing number，首先明确self-dividing number的概念，就是它可以被自己的每一位数整除。那么先想特殊情况，如果位数中有0，则它不可能是self-dividing number，因为除数不能为0。找到所给边界之内的自分数self-dividing number，首先明确self-dividing number的概念，就是它可以被自己的每一位数整除。那么先想特殊情况，如果位数中有0，则它不可能是self-dividing number，因为除数不能为0。