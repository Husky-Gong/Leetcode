# 107 Binary Tree Level Order Traversal II

## Question

 Given a binary tree, return the bottom-up level order traversal of its nodes' values. \(ie, from left to right, level by level from leaf to root\).

For example: Given binary tree \[3,9,20,null,null,15,7\], 3 /  9 20 /  15 7 return its bottom-up level order traversal as: \[ \[15,7\], \[9,20\], \[3\] \] &lt;/pre&gt;

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
    public List<List<Integer>> levelOrderBottom(TreeNode root) {
        List<List<Integer>> res = new LinkedList<List<Integer>>();
        Queue<TreeNode> queue = new LinkedList<TreeNode>();

        if(root == null) return res;

        queue.offer(root);

        while(!queue.isEmpty()){
            int levelNum = queue.size();
            List<Integer> levelList = new LinkedList<Integer>();

            for(int i = 0; i < levelNum; i++){

                if(queue.peek().left != null) queue.offer(queue.peek().left);
                if(queue.peek().right != null) queue.offer(queue.peek().right);

                levelList.add(queue.poll().val);
            }

            res.add(0, levelList);
        }

        return res;
    }
}
```

