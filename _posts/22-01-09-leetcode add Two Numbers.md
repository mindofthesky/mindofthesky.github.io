python3 code 



class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        
        added = ListNode(val = (l1.val + l2.val) % 10);
        carry_over = (l1.val + l2.val) //10;
        current_node = added;
        
        while(l1.next and l2.next):
            
            l1 = l1.next;
            l2 = l2.next;
            
            current_node.next = ListNode(val = (carry_over + l1.val + l2.val) % 10);
            carry_over = (carry_over + l1.val + l2.val) // 10;
            current_node = current_node.next;
            
        while(l1.next):
            l1 = l1.next;
            current_node.next = ListNode(val = (carry_over + l1.val) % 10)
            carry_over = (carry_over + l1.val + l2.val) //10;
            current_node = current_node.next;
            
        while(l2.next):
            l2 = l2.next;
            current_node.next = ListNode(val = (carry_over + l2.val) % 10);
            carry_over = (carry_over + l2.val) //10;
            current_node = current_node.next;
            
        if(carry_over) > 0:
            current_node.next = ListNode(val = 1);
            
        return(added);