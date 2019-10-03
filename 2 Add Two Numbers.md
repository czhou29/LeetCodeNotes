## 2 Add Two Numbers

### Method 1

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
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode *dummy = new ListNode(-1);
        ListNode *curr = dummy;
        int carry = 0;
        while(l1&&l2){
            int temp = l1->val+l2->val+carry;
            curr->next = new ListNode(temp%10);
            carry = temp / 10;
            curr = curr->next;
            l1 = l1->next;
            l2 = l2->next;
        }
        
        while(l1){
            int temp = l1->val + carry;
            curr->next = new ListNode(temp%10);
            carry = temp / 10;
            curr = curr->next;
            l1 = l1->next;
        }
        while(l2){
            int temp = l2->val + carry;
            curr->next = new ListNode(temp%10);
            carry = temp / 10;
            curr = curr->next;
            l2 = l2->next;
        }
        
        if(carry == 1) {
            curr->next = new ListNode(carry);
            curr = curr->next;
        }
        
        return dummy->next;
    }
};
```

### Method 2

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
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode *prehead = new ListNode(0), *p = prehead;
        int carry = 0;
        while(l1 || l2 || carry) {
            int sum = (l1 ? l1->val : 0) + (l2 ? l2->val : 0) + carry;
            carry = sum / 10;
            p->next = new ListNode(sum % 10);
            p = p ->next;
            l1 = l1?l1->next:l1;
            l2 = l2?l2->next:l2;
        }
        return prehead->next;
    }
};
```

