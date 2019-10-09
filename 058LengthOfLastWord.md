# 058 Length of Last Word

## Question

<pre>
Given a string s consists of upper/lower-case alphabets and empty space characters ' ', return the length of last word in the string.

If the last word does not exist, return 0.

Note: A word is defined as a character sequence consists of non-space characters only.

Example:

Input: "Hello World"
Output: 5
</pre>

<div STYLE="page-break-after: always;">

## Solution

```java
class Solution {
    public int lengthOfLastWord(String s) {
    //     String[] a = s.split(" ");
    //     if(a.length > 0) return a[a.length-1].length();
    //     else return 0;
    
    // solution 2:
    s = s.trim();
    int lastIndex = s.lastIndexOf(' ') + 1;
    return s.length() - lastIndex;
    }
}
```
