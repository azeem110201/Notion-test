## Question:

Given `head`, the head of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the `next` pointer. Internally, `pos` is used to denote the index of the node that tail's `next` pointer is connected to. **Note that `pos` is not passed as a parameter**.

Return `true` *if there is a cycle in the linked list*. Otherwise, return `false`.

- **Example**

[Linked List Cycle - LeetCode](https://leetcode.com/problems/linked-list-cycle/)

```python
**# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        ## return False if head is None
        if head == None or head.next == None:
            return False
        ## using the approach of fast and slow pointer. The fast pointer moves two steps ahead of slow pointer
        ## so when fast == slow and loop is detected 
        fast = head.next
        slow = head
        
        while fast != slow:
            if fast == None or fast.next == None or slow == None:
                return False
            slow = slow.next
            fast = fast.next.next
            
        return True**
```

Time complexity of the algorithm is O(n) and space complexity is O(1)