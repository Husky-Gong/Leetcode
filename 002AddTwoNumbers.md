# 2 Add Two Numbers
## Question
<pre>
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Example:

Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
Explanation: 342 + 465 = 807.
</pre>
<div STYLE="page-break-after: always;">

## Solution
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode l3 = dummy;
        int carry = 0;
        
        while(l1 != null && l2 != null){
            int value = (l1.val + l2.val + carry) % 10;
            carry = (l1.val + l2.val + carry) / 10;
            l1 = l1.next;
            l2 = l2.next;
            
            ListNode newNode = new ListNode(value);
            
            l3.next = newNode;
            l3 = newNode;
        }
        
        while(l1 != null){
            int value = (l1.val + carry) % 10;
            carry = (l1.val + carry) / 10;
            
            l1 = l1.next;
            
            ListNode newNode = new ListNode(value);
            
            l3.next = newNode;
            l3 = newNode;
        }
        
        while(l2 != null){
            int value = (l2.val + carry) % 10;
            carry = (l2.val + carry) / 10;
            
            l2 = l2.next;
            
            ListNode newNode = new ListNode(value);
            
            l3.next = newNode;
            l3 = newNode;
        }
        
        if(carry != 0){
            ListNode newNode = new ListNode(carry);
            l3.next = newNode;
            l3 = newNode;
        }
        
        return dummy.next;
    }
}
```
