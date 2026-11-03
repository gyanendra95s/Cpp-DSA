## 01. Search in Sorted Matrix

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/search-in-a-matrix-1587115621/1)

### Problem Description

**Task:** Given a strictly sorted 2D matrix mat[][] and a number x. Find whether the number x is present in the matrix or not.Note: In a strictly sorted matrix, each row is sorted in strictly increasing order, and the first element of the i^th row (i! = 0) is greater than the last element of the (i-1)^th row.Examples:Input: mat[][] = [[1, 5, 9], [14, 20, 21], [30, 34, 43]], x = 14

#### Examples

##### Example 1

- **Output:**
```text
true
```
- **Explanation:** 14 is present in the matrix, so output is true.

##### Example 2

- **Input:**
```text
mat[][] = [[1, 5, 9, 11], [14, 20, 21, 26], [30, 34, 43, 50]], x = 42Output: false
```
- **Explanation:** 101 is present in the matrix.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(log(n * m))
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (2)

#### Solution 1 (C++)

- **Submitted:** 2026-11-03 21:45:01
- **Status:** Correct
- **Marks:** 0

```cpp
class Solution {
  public:
    bool searchMatrix(vector<vector<int>> &mat, int x) {
        // code here
        for(int i=0;i<mat.size();i++){
            for(int j=0;j<mat[i].size();j++){
                if(mat[i][j]==x){
                    return true;
                }
            }
        }
        return false;
    }
};
```

#### Solution 2 (C++)

- **Submitted:** 2025-11-14 23:36:52
- **Status:** Correct
- **Marks:** 4

```cpp
class Solution {
  public:
    bool searchMatrix(vector<vector<int>> &mat, int x) {
        // code here
        for(int i=0;i<mat.size();i++){
            for(int j=0;j<mat[i].size();j++){
                if(mat[i][j]==x){
                    return true;
                }
            }
        }
        return false;
    }
};
```

*Generated on: 11/3/2026, 9:45:33 PM*