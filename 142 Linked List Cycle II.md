## 142 Linked List Cycle II

```c++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        if(!head) return NULL;
        ListNode *dummy = new ListNode(-1);
        dummy->next = head;
        ListNode *s = dummy, *f = dummy;
        while(f && f->next){
            s = s->next;
            f = f->next->next;
            if(s == f) break;
        }
        if(s == f) f = dummy;
        else return NULL;
        while(f!=s){
            s = s->next;
            f = f->next;
        }
        return s;
    }
};
```

