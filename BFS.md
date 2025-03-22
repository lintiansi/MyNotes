***題目***
利用BFS找出Binary tree的最大深度
***code***
public class Solution {
    public int MaxDepth(TreeNode root) {
        if(root == null)
        {
            return 0;
        }
        Queue<TreeNode> queue = new Queue<TreeNode>();//建立一個Queue儲存每層的元素
        int depth = 0;
        queue.Enqueue(root);//把root放入queue
        while(queue.Count>0)
        {
            
            int size = queue.Count;//先計算要走幾次for迴圈
            for(int i = 0;i<size;++i)
            {   
                TreeNode node = queue.Dequeue();//queue中的第一個先看
                if(node.left != null)//將其左右節點放入
               {
                queue.Enqueue(node.left);
               }
            if(node.right != null)
               {
                queue.Enqueue(node.right);
               }

            }++depth;//跑完該層for迴圈深度+1
            
        }return depth;



        
    }
}
***筆記***
要在for迴圈前計算queue.Count來確認此層for迴圈要跑幾次
