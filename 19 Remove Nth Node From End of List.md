##  19 Remove Nth Node From End of List

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
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        ListNode *s = head, *f = head;
        for(int i = 0; i < n; i++) f = f -> next;
        if(!f){
            head = head -> next;
            return head;
        }
        while(f->next) {
            f = f -> next;
            s = s -> next;
        }
        s->next = s->next->next;
        return head;
    }
};
```

