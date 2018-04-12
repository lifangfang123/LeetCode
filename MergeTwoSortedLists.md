# 问题 #
合并两个有序链表
合并两个有序链表并将其作为一个新链表返回。新链表应当由原来的两个链表的结点拼接而成。
# 代码 #
```C
struct ListNode* mergeTwoLists(struct ListNode* l1, struct ListNode* l2) {
    if (!l1 && !l2) return NULL;  
    if (!l1) return l2;  
    if (!l2) return l1;  
    struct ListNode *head, *p;  
    if (l1->val < l2->val){  
        head = p = l1;  
        l1 = l1->next;  
    }  
    else {  
        head = p = l2;  
        l2 = l2->next;  
    }  
    while (l1 && l2){  
        if (l1->val < l2->val){  
            p->next = l1;  
            l1 = l1->next;  
        }  
        else {  
            p->next = l2;  
            l2 = l2->next;  
        }  
        p = p->next;  
    }  
    if (!l1){  
        p->next = l2;  
    }  
    if (!l2){  
        p->next = l1;  
    }  
    return head;  
}  
```
# 总结 #
两个链表上分别设立游标来遍历，同时设立一个表示合并后链表的游标，不停地判断当前两链表的结点值，取小的结点将其拼接在合并后的链表上。由于链表都没有头结点，所以最开始要单独判断一下来获取最后合并链表的头结点。