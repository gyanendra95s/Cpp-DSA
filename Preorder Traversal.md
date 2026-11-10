## 01. Preorder Traversal

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/preorder-traversal/1)

### Problem Description

**Task:** Given the root of a binary tree, return its preorder traversal. A preorder traversal first visits the node, then visits the left child (including its entire subtree), and finally visits the right child (including its entire subtree).

#### Examples

##### Example 1

- **Input:**
```text
root = [1, 4, N, 4, 2]
```
- **Output:**
```text
[1, 4, 4, 2]Explanation: The preorder traversal of the given binary tree is [1, 4, 4, 2]
```

##### Example 2

- **Input:**
```text
root = [6, 3, 2, N, 1, 2, N]
```
- **Output:**
```text
[6, 3, 1, 2, 2] Explanation: The preorder traversal of the given binary tree is [6, 3, 1, 2, 2]
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2025-11-29 21:41:25
- **Status:** Correct
- **Marks:** 1

```cpp
/*
class Node
{
    int data;
    Node* left;
    Node* right;

    Node(int x){
        data = x;
        left = right = NULL;
    }
};
*/

class Solution {
  public:
    vector<int> preOrder(Node* root) {
        
        vector<int>s;
        if(root==NULL){
            return s;
        }
        
        s.push_back(root->data);

        vector<int>left=preOrder(root->left);
        s.insert(s.end(),left.begin(),left.end());

        vector<int>right=preOrder(root->right);
        s.insert(s.end(),right.begin(),right.end());

        return s;
    }
};
```

*Generated on: 11/10/2026, 4:31:53 PM*