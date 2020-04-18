# 083 Remove Duplicates from Sorted List

## Question

 Given a sorted linked list, delete all duplicates such that each element appear only once.

Example 1:

Input: 1-&gt;1-&gt;2 Output: 1-&gt;2

Example 2:

Input: 1-&gt;1-&gt;2-&gt;3-&gt;3 Output: 1-&gt;2-&gt;3 &lt;/pre&gt;

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
    public ListNode deleteDuplicates(ListNode head) {

        if(head == null) return null;
        ListNode curr = head;

        while(curr.next != null){
            int currVal = curr.val;
            while(curr.next.val == currVal){
                curr.next = curr.next.next;
                if(curr.next == null) break;
            }

            curr = curr.next;
            if(curr == null) break;
        }
        return head;
    }
}
```

