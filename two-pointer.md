***題目***
You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return the maximum amount of water a container can store.

Notice that you may not slant the container.
***code***
public class Solution {
    public int MaxArea(int[] height) {
        int left = 0;
        int right = height.Length-1;
        int MaxArea = 0;
        int Area = 0;
        while(left<right)
        {
            int wid = right - left;
            int minHeight = Math.Min(height[left],height[right]);
            Area = minHeight*wid;
            MaxArea = Math.Max(MaxArea,Area);
            if(height[left]>height[right])
            {
                --right;
            }
            else 
            {
                ++left;
            }



        }return MaxArea;
        
    }
}
***筆記***
利用two pointer，當左指標的數字較大時移動右指標(想辦法找到更大的)
利用Math.Max儲存最大的