## DATE : 
## AIM : 
To find the minimum cost path from the top-left cell (0, 0) to a given cell (m, n) in a matrix using Dynamic Programming.

## Algorithm :

1. **Input**: A 2D cost matrix of size `R x C`, and a destination cell `(m, n)`.
2. **Create** a 2D list `tc` of the same size as the cost matrix to store the **minimum cost** to reach each cell.
3. **Initialize**:
   - `tc[0][0]` with `cost[0][0]`.
   - First column `tc[i][0] = tc[i-1][0] + cost[i][0]` for all `i`.
   - First row `tc[0][j] = tc[0][j-1] + cost[0][j]` for all `j`.
4. **Fill the rest** of the matrix:
   - For each cell `(i, j)`, compute the minimum cost from the three possible directions:
     ```python
     tc[i][j] = min(tc[i-1][j-1], tc[i-1][j], tc[i][j-1]) + cost[i][j]
     ```
5. **Output**: The value in `tc[m][n]` is the **minimum cost** to reach the destination.

## Program :
```
DEVELOPED BY : SHALINI K
REGISTER NUMBER : 212222240095

R = int(input())
C = int(input())
def minCost(cost, m, n):
    tc = [[0 for x in range(C)] for x in range(R)]
    tc[0][0] = cost[0][0]
    for i in range(1, m+1):
        tc[i][0] = tc[i-1][0] + cost[i][0]
    for j in range(1, n+1):
        tc[0][j] = tc[0][j-1] + cost[0][j]
    for i in range(1, m+1):
        for j in range(1, n+1):
            tc[i][j] = min(tc[i-1][j-1], tc[i-1][j], tc[i][j-1]) + cost[i][j]
 
    return tc[m][n]
 
cost = [[1, 2, 3],
        [4, 8, 2],
        [1, 5, 3]]
print(minCost(cost, R-1, C-1))
```
## Output :
![image](https://github.com/user-attachments/assets/37851dc4-d7db-4a50-9242-982297aec3e4)

## Result:
Thus, the program was executed successfully for computing the minimum cost path using Dynamic Programming.

