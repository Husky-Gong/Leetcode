# 011 Container With Most Water
## Question
<pre>
Given n non-negative integers a1, a2, ..., an , where each represents a point at coordinate (i, ai). n vertical lines are drawn such that the two endpoints of line i is at (i, ai) and (i, 0). Find two lines, which together with x-axis forms a container, such that the container contains the most water.

Note: You may not slant the container and n is at least 2.

Example:

Input: [1,8,6,2,5,4,8,3,7]
Output: 49
</pre>
<div STYLE="page-break-after: always;">

## Solution
```java
class Solution {
    public int maxArea(int[] height) {
        int left = 0, right = height.length - 1;
        
        int maxHeight = 0, maxArea = 0;
        
        while(left < right){
            if(height[left] > maxHeight && height[right] > maxHeight){
                maxHeight = Math.min(height[left], height[right]);
                maxArea = Math.max(maxArea, maxHeight * (right - left));
            }
            
            // update bound points
            if(height[left] == height[right]){
                left ++;
                right --;
            }
            else if(height[left] > height[right]) right --;
            else left ++;
        }
        
        return maxArea;
    }
}
```
