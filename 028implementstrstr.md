# 028 Implement strStr\(\)

## Question

```text

Implement strStr().

Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

Example 1:

Input: haystack = "hello", needle = "ll"
Output: 2
Example 2:

Input: haystack = "aaaaa", needle = "bba"
Output: -1
Clarification:

What should we return when needle is an empty string? This is a great question to ask during an interview.

For the purpose of this problem, we will return 0 when needle is an empty string. This is consistent to C's strstr() and Java's indexOf().
```

## Solution

```java
class Solution {
    public int strStr(String haystack, String needle) {
        // return haystack.indexOf(needle);

        int l1 = haystack.length();
        int l2 = needle.length();

        if(l1<l2) return -1;
        else if(l2==0) return 0;

        int range = l1 - l2;
        for(int i = 0; i <= range; i++){
            if(haystack.substring(i, i+l2).equals(needle)) return i;
        }

        return -1;
    }
}
```

