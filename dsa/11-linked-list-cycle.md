python code:
class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
            slow = head
            fast = head
            while fast is not None and fast.next is not None:
                  slow = slow.next
                  fast = fast.next.next
                  if slow == fast:
                      return True
            return False
algorithm :
here for this problem we use floyd cycle detection algorithm we we consider two pointer in the list as slow and fast
both the pointers will start from head
and while fast and fast.next is not None which means given list is an endless cycle linked list
we shift pointers according i.e, slow = slow.next and fast = fast.next.next
while continuing in the condition if slow == fast then we return True or we return False
