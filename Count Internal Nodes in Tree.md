## 01. Count Internal Nodes in Tree

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/count-non-leaf-nodes-in-tree/1)

### Problem Description

**Task:** Given a root of a Binary Tree. Count all the non-leaf nodes present in the given binary tree and return it.Examples:Input: root[] = [1, 2, 3, 4, 5]

#### Examples

##### Example 1

- **Output:**
```text
3
```
- **Explanation:** Nodes 8, 3 and 6 are the only non leaf nodes.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(h)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-11-10 16:13:13
- **Status:** Correct
- **Marks:** 1

```cpp
/* Binary Tree Node Structure
class Node {
    public:
    int data;
    Node *left;
    Node *right;

    Node(int val) {
        data = val;
        left = right = nullptr;
    }
};
*/

class Solution {
  public:
    int countNonLeafNodes(Node* root) {
        // code here
        if(root==NULL){
            return 0;
        }
        if(root->left==NULL && root->right==NULL){
            return 0;
        }
        
        return 1+countNonLeafNodes(root->left)+countNonLeafNodes(root->right);
    }
};
```

*Generated on: 11/10/2026, 4:13:42 PM*