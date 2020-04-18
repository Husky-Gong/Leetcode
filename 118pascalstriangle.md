# 118 Pascal's Triangle

## Question

 Given a non-negative integer numRows, generate the first numRows of Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it.

Example:

Input: 5 Output: \[ \[1\], \[1,1\], \[1,2,1\], \[1,3,3,1\], \[1,4,6,4,1\] \] &lt;/pre&gt; ![Alt text](https://github.com/Husky-Gong/Leetcode/tree/97ce6169b2cd8fe98d667ec2641a73011cd8116a/PascalTriangleAnimated2.gif)

## Solution

```java
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> allRows = new ArrayList<List<Integer>>();
        List<Integer> row = new ArrayList<Integer>();

        for(int i = 0; i < numRows; i++){
            row.add(0,1);
            for(int j = 1; j < row.size() - 1; j ++){
                row.set(j, row.get(j) + row.get(j+1));
            }
            allRows.add(new ArrayList<Integer>(row));
        }

        return allRows;
    }
}
```

