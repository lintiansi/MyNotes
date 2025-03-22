***題目:You are given a string s, which contains stars *.

In one operation, you can:

Choose a star in s.
Remove the closest non-star character to its left, as well as remove the star itself.
Return the string after all stars have been removed.
***
***code:***
public class Solution {
    public string RemoveStars(string s) {
        Stack<char> stack = new Stack<char>();\\建立Stack儲存刪掉'*'及它左邊的char
        Stack<char> stack1 = new Stack<char>();\\反轉stack
        foreach(char c in s)\\當stack.Count>0時，遇到'*'時Pop最上面的char，且不儲存'*'
        {
            if(c =='*')
            {
                if(stack.Count>0)
                {
                    stack.Pop();
                }
            }
            else
            {
                stack.Push(c);
            }
        }
        foreach(char i in stack)
        {
            stack1.Push(i);
        }
        return new string (stack1.ToArray());        
    }
}
***notes***
stack為LIFO，最後進去的先出來。
stack.Pop()移除最上面的元素
stack.Push(i)將i按照順序存入stack
stack.Peek()查看最上面的元素(和Queue.Peek()相同)
stack.Count查看數量
