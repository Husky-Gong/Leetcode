# 014 Longest Common Prefix

## Question
<pre>
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

Example 1:

Input: ["flower","flow","flight"]
Output: "fl"
Example 2:

Input: ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.

Note:
All given inputs are in lowercase letters a-z.
</pre>

## Solution
```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        if(strs == null || strs.length == 0) return "";
        
        String preFix = strs[0];
        
        for(int i = 0; i < strs.length; i++){
            while(strs[i].indexOf(preFix) != 0){
                preFix = preFix.substring(0, preFix.length()-1);
            }
        }
        return preFix;
    }
}
```
