# 168 Excel Sheet Column Title

## Question

 Given a positive integer, return its corresponding column title as appear in an Excel sheet.

For example:

```text
1 -> A
2 -> B
3 -> C
...
26 -> Z
27 -> AA
28 -> AB 
...
```

Example 1:

Input: 1 Output: "A" Example 2:

Input: 28 Output: "AB" Example 3:

Input: 701 Output: "ZY" &lt;/pre&gt;

## Solution

```java
class Solution {
    public String convertToTitle(int n) {
        StringBuilder result = new StringBuilder();

        while(n > 0){
            n--;
            result.append((char)('A' + n % 26));
            n = n / 26;
        }

        result = result.reverse();
        return result.toString();
    }
}
```

