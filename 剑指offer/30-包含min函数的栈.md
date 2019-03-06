# 题目

定义栈的数据结构，请在该类型中实现一个能够得到栈中所含最小元素的min函数（时间复杂度应为O（1））。

## 思路

如果利用利用一个标识来记录的话，只能记录当前的。再出栈后还得重新再进行计算，不是个好的方法。

可以使用两个栈来操作，最小值一定在最顶部，而且出栈后更小值在下一个

## 代码实现


```
    Stack<Integer> dataStack = new Stack<>();
    Stack<Integer> minStack = new Stack<>();
    
    public void push(int node) {
        dataStack.push(node);
        minStack.push(minStack.isEmpty() ? node : Math.min(node,minStack.peek()));
    }
    
    public void pop() {
        dataStack.pop();
        minStack.pop();
    }
    
    public int top() {
        return dataStack.peek();
    }
    
    public int min() {
        return minStack.peek();
    }
```
