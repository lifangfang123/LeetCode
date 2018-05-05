# 问题 #
给定一个链表，判断链表中是否有环。
# 代码 #
```C
 class Solution {  
    public:  
        bool hasCycle(ListNode *head) {  
            ListNode* first=head;  
            ListNode* second=head;  
            while(first!=NULL&&second!=NULL&&second->next!=NULL){ //注意这个条件判断不能写漏了。  
                first=first->next;  
                second=second->next->next;  
                if(first==second)  
                    return true;  
            }  
            return false;  
        }  
    };  
```
# 总结 #
若要判断一个链表是否有环，可设计快慢指针，当快慢指针都进入环的时候，若最终两个指针相遇，必可说明链表存在环。
