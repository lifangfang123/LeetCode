# 问题 #
初始位置 (0, 0) 处有一个机器人。给出它的一系列动作，判断这个机器人的移动路线是否形成一个圆圈，换言之就是判断它是否会移回到原来的位置。
移动顺序由一个字符串表示。每一个动作都是由一个字符来表示的。机器人有效的动作有 R（右），L（左），U（上）和 D（下）。输出应为 true 或 false，表示机器人移动路线是否成圈。
# 代码 #
```C
    class Solution {  
    public:  
        bool judgeCircle(string moves) {  
              
            if(moves.length() == 0) return true;  
            if(moves.length() %2 != 0) return false;  
              
            int up_or_down = 0; //向上加1，向下减1  
            int left_or_right = 0;  
            for(int i = 0; i < moves.length(); i ++) {  
                if(moves[i] == 'U') up_or_down ++;  
                else if(moves[i] == 'D') up_or_down --;  
                else if(moves[i] == 'L') left_or_right ++;  
                else if(moves[i] == 'R') left_or_right --;  
            }  
              
            if(up_or_down == 0 && left_or_right == 0)  
                return true;  
            return false;  
        }  
    };  
```
# 总结 #
如果机器人走回最初位置，那么机器人向上移动的步数应该等于向下移动的步数并且向左移动的步数应该等于向右移动的步数