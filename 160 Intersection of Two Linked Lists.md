## 160 Intersection of Two Linked Lists

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
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode *hA = headA, *hB = headB;
        bool sA = false, sB = false;
        while(hA != hB) {
            if(hA) hA = hA->next;
            else {hA = headB; sA = true;}
            if(hB) hB = hB->next;
            else {hB = headA; sB = true;}
            if(!hA&&!hB&&sA&&sB) break;
        }
        return hA;
    }
};
```

