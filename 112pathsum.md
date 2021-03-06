# 112 Path Sum

## Question

```text

Given a binary tree and a sum, determine if the tree has a root-to-leaf path such that adding up all the values along the path equals the given sum.

Note: A leaf is a node with no children.

Example:

Given the below binary tree and sum = 22,

      5
     / \
    4   8
   /   / \
  11  13  4
 /  \      \
7    2      1
return true, as there exist a root-to-leaf path 5->4->11->2 which sum is 22.
```

## Solution

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public boolean hasPathSum(TreeNode root, int sum) {
        Stack<TreeNode> stack = new Stack<TreeNode>();
        Stack<Integer> sums = new Stack<Integer>();

        stack.push(root);
        sums.push(sum);

        while((!stack.isEmpty()) && root != null){
            int value = sums.pop();
            TreeNode top = stack.pop();

            if(top.left == null & top.right == null & value == top.val){
                return true;
            }

            if(top.right != null){
                stack.push(top.right);
                sums.push(value - top.val);
            }

            if(top.left != null){
                stack.push(top.left);
                sums.push(value - top.val);
            }
        }

        return false;
    }
}
```

