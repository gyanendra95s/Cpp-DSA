## 01. Inorder Traversal

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/inorder-traversal/1)

### Problem Description

**Task:** Given a root of a Binary Tree, your task is to return its Inorder Traversal.

> **Note:** An inorder traversal first visits the left child (including its entire subtree), then visits the node, and finally visits the right child (including its entire subtree).

#### Examples

##### Example 1

- **Input:**
```text
root = [1, 2, 3, 4, 5]
```
- **Output:**
```text
[4, 2, 5, 1, 3]Explanation: The inorder traversal of the given binary tree is [4, 2, 5, 1, 3].
```

##### Example 2

- **Input:**
```text
root = [8, 1, 5, N, 7, 10, 6, N, 10, 6]
```
- **Output:**
```text
[1, 7, 10, 8, 6, 10, 5, 6]Explanation: The inorder traversal of the given binary tree is [1, 7, 10, 8, 6, 10, 5, 6].
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2025-11-29 22:55:03
- **Status:** Correct
- **Marks:** 2

```cpp
/*
class Node {
  public:
    int data;
    Node* left;
    Node* right;

    Node(int val) {
        data = val;
        left = NULL;
        right = NULL;
    }
};
*/

class Solution {
  public:
    vector<int> inOrder(Node* root) {
        // code here
        vector<int>s;
        if(root==NULL){
            return s;
        }
        
         vector<int>left=inOrder(root->left);
        s.insert(s.end(),left.begin(),left.end());

        s.push_back(root->data);

        vector<int>right=inOrder(root->right);
        s.insert(s.end(),right.begin(),right.end());

        return s;
    }
};
```

*Generated on: 11/10/2026, 4:24:11 PM*