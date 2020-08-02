## 82 Remove Duplicates from Sorted List II

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
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode *dummy = new ListNode(0);
        dummy->next = head;
        ListNode *tm = dummy;
        ListNode *t = head;
        while(t && t->next) {
            bool f = false;
            while(t && t->next && t->val == t->next->val) {
                t = t->next;
                f = true;
            }
            if(f) tm->next = t->next;
            if(!f) tm = tm->next;
            t = t->next;
        }
        return dummy->next;
    }
};
```

