## 01. Middle of Stack

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/middle-of-stack/1)

### Problem Description

**Task:** Given a stack st[] of size n, find the middle element of the stackNote: In case of even elements, return the first middle from bottom.Examples:Input: st[] = [1, 2, 3, 4, 5]

#### Examples

##### Example 1

- **Output:**
```text
2
```
- **Explanation:** The two middle elements are 2 and 3. Since we need the middle element closer to the bottom, the answer is 2.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-11-06 22:18:17
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
    int stackMiddle(stack<int>& st) {
        // code here
        vector<int>ans;
        
        while(!st.empty()){
            ans.push_back(st.top());
            st.pop();
        }
        
        int mid=ans.size()/2;
        return ans[mid];
    }
};
```

*Generated on: 11/6/2026, 10:18:47 PM*