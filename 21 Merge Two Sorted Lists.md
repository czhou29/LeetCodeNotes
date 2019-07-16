## 21 Merge Two Sorted Lists

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
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        ListNode *dummy = new ListNode(-1);
        ListNode *curr = dummy;
        ListNode *l1c = l1, *l2c = l2;
        while(l1c && l2c){
            if(l1c->val<l2c->val){
                curr->next = l1c;
                curr = curr->next;
                l1c = l1c->next;
            }
            else {
                curr->next = l2c;
                curr = curr->next;
                l2c = l2c->next;
            }
        }
        
        while(l1c){
            curr->next = l1c;
            curr = curr->next;
            l1c = l1c->next;
        }

        while(l2c){
            curr->next = l2c;
            curr = curr->next;
            l2c = l2c->next;
        }
        return dummy->next;
    }
};
```

