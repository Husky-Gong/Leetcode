# 171 Excel Sheet Column Number
## Question
<pre>
Given a column title as appear in an Excel sheet, return its corresponding column number.

For example:

    A -> 1
    B -> 2
    C -> 3
    ...
    Z -> 26
    AA -> 27
    AB -> 28 
    ...
Example 1:

Input: "A"
Output: 1
Example 2:

Input: "AB"
Output: 28
Example 3:

Input: "ZY"
Output: 701
</pre>
<div STYLE="page-break-after: always;">

## Solution
```java
class Solution {
    public int titleToNumber(String s) {
        int res = 0;
        if(s == null || s.length() == 0) return res;
        
        char[] list = s.toCharArray();
        
        for(int i = 0; i < list.length; i ++){
            int temp = (int)list[i] - 'A' + 1;
            res += temp * Math.pow(26,list.length - i - 1);
        }
        return res;
    }
}
```
