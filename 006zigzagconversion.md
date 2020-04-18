# 006 ZigZag Conversion

## Question

 The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: \(you may want to display this pattern in a fixed font for better legibility\)

P A H N A P L S I I G Y I R And then read line by line: "PAHNAPLSIIGYIR"

Write the code that will take a string and make this conversion given a number of rows:

string convert\(string s, int numRows\); Example 1:

Input: s = "PAYPALISHIRING", numRows = 3 Output: "PAHNAPLSIIGYIR" Example 2:

Input: s = "PAYPALISHIRING", numRows = 4 Output: "PINALSIGYAHRPI" Explanation:

P I N A L S I G Y A H R P I &lt;/pre&gt;

## Solution

```java
class Solution {
    public String convert(String s, int numRows) {
        char[] charArray = s.toCharArray();
        int charNum = charArray.length;

        StringBuffer[] sb = new StringBuffer[numRows];

        for(int i = 0; i < numRows; i++){
            sb[i] = new StringBuffer();
        }

        int count = 0;

        while(count < charNum){
            for(int idx = 0; idx < numRows && count < charNum; idx ++){
                sb[idx].append(charArray[count]);
                count ++;
            }

            for(int idx = numRows - 2; idx >= 1 && count < charNum; idx --){
                sb[idx].append(charArray[count]);
                count ++;
            }
        }

        for(int i = 1; i < numRows; i ++){
            sb[0].append(sb[i]);
        }

        return sb[0].toString();
    }
}
```

