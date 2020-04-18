# 067 Add Binary

## Question

 Given two binary strings, return their sum \(also a binary string\).

The input strings are both non-empty and contains only characters 1 or 0.

Example 1:

Input: a = "11", b = "1" Output: "100" Example 2:

Input: a = "1010", b = "1011" Output: "10101" &lt;/pre&gt;

## Solution

```java
class Solution {
    // StringBuilder.append 是往后面加
    public String addBinary(String a, String b) {
        StringBuilder res = new StringBuilder();
        int i = a.length()-1;
        int j = b.length()-1;
        int carry = 0;

        while(i >= 0 || j >= 0){
            int sum = carry;
            if(i >= 0) sum += a.charAt(i--) - '0';
            if(j >= 0) sum += b.charAt(j--) - '0';

            carry = sum / 2;
            sum = sum % 2;
            res.append(sum);
        }

        if(carry != 0) res.append(carry);
        return res.reverse().toString();
    }
}
```

