## 203 Remove Linked List Elements

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
    ListNode* removeElements(ListNode* head, int val) {
        if(!head) return head;
        ListNode *dummy = new ListNode(-1), *curr = dummy;
        dummy->next = head;
        
        while(curr) {
            if(curr->next && curr->next->val == val)
                curr->next = curr->next->next;
            else
                curr = curr->next;  
        }
        return dummy->next;
    }
};
```

