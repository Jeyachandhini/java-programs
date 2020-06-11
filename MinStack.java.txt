class MinStack {
    Stack<Integer> stack = new Stack<Integer>();
    Stack<Integer> minHistory = new Stack<Integer>();
    /** initialize your data structure here. */
    public MinStack() {
    
    }
    
    public void push(int x) {
        stack.push(x);
        if((minHistory.empty()) || minHistory.peek()>x)
        {
            minHistory.push(x);
        }
    }
    
    public void pop() {
        if(stack.peek()==minHistory.peek())
        {
            minHistory.pop();
        }
        stack.pop();
    }
    
    public int top() {
        return stack.peek();
    }
    
    public int getMin() {
        return minHistory.peek();
    }
}