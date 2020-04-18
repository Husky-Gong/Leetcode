# 003 Longest Substring Without Repeating Characters

## Question

 Given a string, find the length of the longest substring without repeating characters.

Example 1:

Input: "abcabcbb" Output: 3 Explanation: The answer is "abc", with the length of 3. Example 2:

Input: "bbbbb" Output: 1 Explanation: The answer is "b", with the length of 1. Example 3:

Input: "pwwkew" Output: 3 Explanation: The answer is "wke", with the length of 3. Note that the answer must be a substring, "pwke" is a subsequence and not a substring. &lt;/pre&gt;

## Solution

```java
class Solution {
    public int lengthOfLongestSubstring(String s) {
        if(s == null || s.length() == 0) return 0;

        int[] charList = new int[256];
        int result = 0;

        for(int i = 0, j = 0; i < s.length(); i ++){
            j = (charList[s.charAt(i)] > 0) ? Math.max(j , charList[s.charAt(i)]) : j;
            charList[s.charAt(i)] = i + 1;
            result = Math.max(result, i - j + 1);
        }
        return result;
    }
}
```

