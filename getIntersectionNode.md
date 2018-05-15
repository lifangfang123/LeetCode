# 问题 #
编写一个程序，找到两个单链表相交的起始节点。
# 代码 #
```C
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
       ListNode *p1 = headA;
        ListNode *p2 = headB;           
        if (p1 == NULL || p2 == NULL) return NULL; 
        while (p1 != NULL && p2 != NULL && p1 != p2) {
            p1 = p1->next;
            p2 = p2->next;
            if (p1 == p2) return p1;
            if (p1 == NULL) p1 = headB;
            if (p2 == NULL) p2 = headA;
        }
        return p1;  
    }
};
```
# 总结 #
先让一边得到链表的长度差。因为最后相同部分的长度相同，所以只要让长的链表先走完长度差，然后同时走，必然会在交叉点处相遇。