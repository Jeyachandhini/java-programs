class MergeTwoSortedList{
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        ListNode result=new ListNode();
        ListNode current=result;
        while(l1!=null && l2!=null)
        {
            if(l1.val<l2.val)
            {
                current.next=l1;
                l1=l1.next; 
            }
            else if(l2.val<l1.val)
            {
                current.next=l2;
                l2=l2.next;
            }
            else
            {
                current.next=l1;
                l1=l1.next;
                current=current.next;
                current.next=l2;
                l2=l2.next;
            }
            current=current.next; 
        }
        if(l1!=null)
        {
            current.next=l1;
            current=current.next; 
            l1=l1.next;
        }
        if(l2!=null)
        {
            current.next=l2;
            current=current.next;  
            l2=l2.next;
        }
        return result.next;
    }
}