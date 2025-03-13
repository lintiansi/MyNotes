***題目***
Given a binary array nums and an integer k, return the maximum number of consecutive 1's in the array if you can flip at most k 0's.
***code***
public class Solution {
    public int LongestOnes(int[] nums, int k) {
        int count = 0;
        int left = 0;
        int right = 0;
        int Len = 0;
        int max = 0;
        for(right = 0;right<nums.Length;++right)
        {
            if(nums[right] == 0)
            {
                ++count;
            }
            while(count>k)
            {
             if(nums[left]==0)
             {
               --count;
             }++left;
             
            }
          Len = right - left +1;
          max = Math.Max(max,Len);  
        }
       return max; 
    }
}

