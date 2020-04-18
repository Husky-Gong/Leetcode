# 005 Longest Palindromic Substring

## Question

 Given a string s, find the longest palindromic substring in s. You may assume that the maximum length of s is 1000.

Example 1:

Input: "babad" Output: "bab" Note: "aba" is also a valid answer. Example 2:

Input: "cbbd" Output: "bb" &lt;/pre&gt;

## Solution

```java
class Solution {
    public String longestPalindrome(String s) {
        // check whether the String isEmpty;
        //set a function to expend the palindromic string length when its left and right point doesn't get out of bound and left and right values are equal. Then expand the right and the left;
        //when it's a odd string, the palindromic substring starts at (center - length/2) and it ends at (center + length/2)
        //when it's even string, the palindromic substring starts at (center -length/2) and it ends at (center-1+length/2)

        int maxLength = 0;
        int start = 0;
        int end = 0;

        if(null==s || s.length() == 0){return "";}

        for(int i = 1; i<s.length(); i++){
            //odd
            int len1 = extendCenter(s, i, i);
            //even
            int len2 = extendCenter(s, i-1, i);

            if(len1>maxLength){
                //是使用len2，而不是maxLength
                start = i - len1/2;
                end = i + len1/2;
                maxLength = len1;
            }

            if(len2>maxLength){
                //是使用len2，而不是maxLength
                start = i - len2/2;
                end = i-1 + len2/2;
                maxLength = len2;
            }
        }

        return s.substring(start,end+1);
    }

     private int extendCenter(String str, int low, int high){
            int maxLength = 1;
         //str[low]==str[high]
            while(low >= 0 && high < str.length() && str.charAt(low)==str.charAt(high)){
                maxLength = high - low + 1;
                low = low-1;
                high = high+1;  
            }
            return maxLength;
        }
}
```

