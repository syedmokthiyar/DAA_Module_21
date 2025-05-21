# EX 3B Hamiltonian Circuit Problem
## DATE:
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1. A graph G with V vertices (represented as an adjacency matrix or adjacency list).

2. Use backtracking to explore all possible paths.

3. Keep a list of visited vertices and a path array.

4. At each step, try all unvisited neighbors.

5. Base Case:

6. If the path contains all vertices exactly once, a Hamiltonian path exists.

## Program:

Developed by:  GANESH R

Register Number:  212222240029

```python
def Hamiltonian_path(adj, N):
    ######################### Add your Code here ##########################
    #Start here
    dp = [[False for i in range(1 << N)] for j in range(N)]
    for i in range(N):
        dp[i][1 << i] = True
    for i in range(1 << N):
        for j in range(N):
            if ((i & (1 << j)) != 0):
 
                for k in range(N):
                    if ((i & (1 << k)) != 0 and
                             adj[k][j] == 1 and
                                     j != k and
                          dp[k][i ^ (1 << j)]):
                        dp[j][i] = True
                        break
    for i in range(N):
        if (dp[i][(1 << N) - 1]):
            return True
    return False
    #End here
    
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")

```

## Output:
![image](https://github.com/user-attachments/assets/459e9ae4-44a9-42f4-ab02-7fcaa0a007a4)



## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
