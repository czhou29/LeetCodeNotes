## 24 Swap Nodes in Pairs

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
    ListNode* swapPairs(ListNode* head) {
        if(!head) return NULL;
        ListNode *dummy = new ListNode(-1);
        dummy->next = head;
        
        ListNode *mae = dummy, *naka = head, *tsugi = head->next;
        
        while(mae && tsugi){
            mae->next = tsugi;
            naka->next = tsugi->next;
            tsugi->next = naka;
            mae = mae->next->next;
            naka = naka->next;
            if(!naka) return dummy->next;
            tsugi = tsugi->next->next->next;
        }
        return dummy->next;
    }
};
```

