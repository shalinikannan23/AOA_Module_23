# EX 5A Minimum Cost Path
## DATE:
## AIM:
To write a Python program using A Naive recursive implementation of Minimum Cost Path Problem.


## Algorithm:

1. **Handle Base Cases:**  
   - If the destination cell `(m, n)` is out of bounds, return the maximum possible integer to indicate an invalid path.  
   - If the starting cell `(0, 0)` is reached, return the cost of that cell, as no more movement is required.  

2. **Recursive Cost Calculation:**  
   - If the current cell is not the starting cell, add its cost to the minimum cost required to reach it from one of its possible neighbors:  
   - **Possible moves:**  
     - Diagonal `(m-1, n-1)`  
     - Up `(m-1, n)`  
     - Left `(m, n-1)`  

3. **Custom Minimum Function:**  
   - Use a custom `min()` function to select the smallest cost among the possible moves to ensure you get the minimum cost path.  

4. **Return the Minimum Cost:**  
   - Return the minimum cost calculated from the above steps as the final result.  

## Program:
```
/*
A program to implement to find the Minimum Cost Path Problem using a  Naive recursive Approach.

Developed by: SHALINI K
Register Number: 212222240095
*/


R = int(input())
C = int(input())
import sys
def minCost(cost, m, n):
    if (n < 0 or m < 0):
        return sys.maxsize
    elif (m == 0 and n == 0):
        return cost[m][n]
    else:
        return cost[m][n] + min( minCost(cost, m-1, n-1),
                                minCost(cost, m-1, n),
                                minCost(cost, m, n-1) )
def min(x, y, z):
    if (x < y):
        return x if (x < z) else z
    else:
        return y if (y < z) else z
cost= [ [1, 2, 3],
        [4, 8, 2],
        [1, 5, 3] ]
print(minCost(cost, R-1, C-1))
```

## Output:

![image](https://github.com/user-attachments/assets/6411ba3f-eaa8-439f-902f-f0bfeb4ac481)

## Result:
Thus the above program was executed successfully for finding the minimum cost.
