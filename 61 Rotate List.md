## 61 Rotate List

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
    ListNode* rotateRight(ListNode* head, int k) {
        if(head == NULL) return NULL;
        ListNode *t = head; int l = 0;
        while(t){
            l++;
            t = t->next;
        }
        if(l) k %= l;
        if(!k) return head;
        
        ListNode *dummy = new ListNode(-1);
        dummy->next = head;
        
        t = head;
        ListNode *tt = head;
        
        for(int i = 0; i < k; i++) tt=tt->next;
        while(tt && tt->next){
            t = t->next;
            tt = tt->next;
        }
        
        dummy->next = t->next;
        tt->next = head;
        t->next = NULL;
        return dummy->next;
        
    }
};
```

