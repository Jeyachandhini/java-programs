class AddTwoNumber{
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode result =new ListNode();
        ListNode current = result;
        int d1,d2,sum,carry=0;
        while( l1!=null && l2!=null )
        {
            d1=(l1!=null)?l1.val:0;
            d2=(l2!=null)?l2.val:0;
            sum=d1+d2+carry;
            if(sum>9)
            {
                carry=sum/10;
                sum=sum%10;
            }
            else
            {
                carry=0;
            }
            current .next=new ListNode(sum);
            current =current .next;
            l1=l1.next;
            l2=l2.next;
            
        }
        while(l1!=null)
        {
            sum=l1.val+carry;
            if(sum>9)
            {
                carry=sum/10;
                sum=sum%10;
            }
            else
            {
                carry=0;
            }
            current.next=new ListNode(sum);
            current=current.next;
            l1=l1.next;
        }
        while(l2!=null)
        {
            sum=l2.val+carry;
            if(sum>9)
            {
                carry=sum/10;
                sum=sum%10;
            }
            else
            {
                carry=0;
            }
            current.next=new ListNode(sum);
            current=current.next;
            l2=l2.next;
        }
        if(carry>0)
        {
           current.next=new ListNode(carry);
           current=current.next; 
        }
        return result.next;
    }
   
}