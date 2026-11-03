## 01. Bipartite Graph

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/bipartite-graph/1)

### Problem Description

**Task:** Given an undirected graph represented by an adjacency list adj[][], check whether the graph is bipartite or not.A bipartite graph is a graph whose vertices can be colored using two colors such that no two adjacent vertices have the same color. Equivalently, the vertices can be divided into two disjoint sets such that:Every edge connects a vertex from one set to a vertex in the other set.No edge connects two vertices within the same set.Examples:Input: adj[][] = [[1], [0, 2], [1]]

#### Examples

##### Example 1

- **Output:**
```text
true
```
- **Explanation:** The vertices can be colored using two colors such that every pair of adjacent vertices has different colors.Input: adj[][] = [[1, 2], [0, 2], [0, 1]]Output: false Explanation: The vertices form a triangle, so it is not possible to color them using two colors without two adjacent vertices having the same color.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(V + E)
- **Expected Auxiliary Space Complexity:** O(V)

### Accepted Solutions (2)

#### Solution 1 (C++)

- **Submitted:** 2026-10-27 23:32:27
- **Status:** Correct
- **Marks:** 0

```cpp
class Solution {
  public:
    bool Bipartite(int i,vector<bool>&vis,vector<bool>&color,list<int>l[]){
        queue<int>q;
        q.push(i);
        vis[i]=true;
        color[i]=0;

        while(!q.empty()){
            int curr=q.front();
            q.pop();

            list<int>neighbour=l[curr];

            for(int v:neighbour){
                if(!vis[v]){
                    vis[v]=true;
                    // curr agar white hai to uska neighbour ko black color kar do
                    color[v]=!color[curr];
                    q.push(v);
                }
                else{
                    if(color[v]==color[curr]){
                        return false;
                    }
                }
            }
        }
        return true;
    }
    bool isBipartite(int V, vector<vector<int>> &edges) {

        // Adjacency List
        list<int>l[V];
        for(int i=0;i<edges.size();i++){
            int u=edges[i][0];
            int v=edges[i][1];

            l[u].push_back(v);
            l[v].push_back(u);
        }

        vector<bool>vis(V,false);
        vector<bool>color(V,-1);

        for(int i=0;i<V;i++){
            if(!vis[i]){
                if(!Bipartite(i,vis,color,l)){
                    return false;
                }
            }
        }
        return true;
    }
};
```

#### Solution 2 (C++)

- **Submitted:** 2026-03-27 16:53:39
- **Status:** Correct
- **Marks:** 4

```cpp
class Solution {
  public:
    bool Bipartite(int i,vector<bool>&vis,vector<bool>&color,list<int>l[]){
        queue<int>q;
        q.push(i);
        vis[i]=true;
        color[i]=0;
        
        while(!q.empty()){
            int curr=q.front();
            q.pop();
            
            list<int>neighbour=l[curr];
            
            for(int v:neighbour){
                if(!vis[v]){
                    vis[v]=true;
                    // curr agar white hai to uska neighbour ko black color kar do
                    color[v]=!color[curr];
                    q.push(v);
                }
                else{
                    if(color[v]==color[curr]){
                        return false;
                    }
                }
            }
        }
        return true;
    }
    bool isBipartite(int V, vector<vector<int>> &edges) {
        
        // Adjacency List
        list<int>l[V];
        for(int i=0;i<edges.size();i++){
            int u=edges[i][0];
            int v=edges[i][1];
            
            l[u].push_back(v);
            l[v].push_back(u);
        }
        
        vector<bool>vis(V,false);
        vector<bool>color(V,-1);
        
        for(int i=0;i<V;i++){
            if(!vis[i]){
                if(!Bipartite(i,vis,color,l)){
                    return false;
                }
            }
        }
        return true;
    }
};
```

*Generated on: 11/4/2026, 12:07:01 AM*