 问题 #
反转一个单链表。
# 代码 #
```C++
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
   if(head==nullptr||head->next==nullptr)
        {
            return head;
        }
        ListNode *p=head;
        head=reverseList(p->next);
        p->next->next=p;
        p->next=nullptr;
        return head;  
    }
};
```
# 总结 #
用递归的方法,先反转后续节点，在反转当前节点。