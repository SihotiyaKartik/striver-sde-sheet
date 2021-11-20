[Add two numbers as a linked list](https://leetcode.com/problems/add-two-numbers/)

```cpp

/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode* l3 = new ListNode(0);
        ListNode* p = l1;
        ListNode* q = l2;
        ListNode* r = l3;
        int carry = 0;
        while(p!= NULL || q!=NULL){
            int x = (p!=NULL) ? p->val:0;
            int y = (q!=NULL) ? q->val:0;
            int sum = x+y+carry;
            carry = sum/10;
            r->next = new ListNode(sum%10);
            r=r->next;
            if(p!=NULL)p=p->next;
            if(q!=NULL)q=q->next;
            
        }
        if(carry>0){
             r->next = new ListNode(carry);
        }
        return l3->next;
    }
};

```