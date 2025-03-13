***題目***
Given a binary array nums, you should delete one element from it.

Return the size of the longest non-empty subarray containing only 1's in the resulting array. Return 0 if there is no such subarray.
***code***
public class Solution {
    public int LongestSubarray(int[] nums) {
        int left = 0;
        
        int count = 0;
        int maxLength = 0;//需要儲存最大值才能確保歷遍又回傳最大值
        for(int right = 0;right<nums.Length;++right)
        {
            if(nums[right]==0)
            {
                ++count;
            }
        
        while(count>1)//移動left直到count<1
        {
            if(nums[left]==0)
            {
                --count;
            }++left;

        }
        maxLength = Math.Max(maxLength,right-left);
        }
        return maxLength;
    }
}
***筆記***
可以改變sliding window的大小
用最大值儲存
