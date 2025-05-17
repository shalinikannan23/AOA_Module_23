# EX 5D Minimum Jump to Reach End Array
## DATE:
## AIM:
To write a python program for finding the minimum number of jumps needed to reach end of the array using Dynamic Programming.


## Algorithm:

1. **Handle Edge Cases:**  
   - If the array is empty or the first element is `0`, return **infinity** as it is not possible to move forward.  

2. **Initialize the Jumps Array:**  
   - Create a `jumps` array of size `n` to store the minimum jumps required to reach each position.  
   - Set the first element (`jumps[0]`) to `0` since no jumps are needed to stay at the starting position.  

3. **Fill the Jumps Array:**  
   - For each position `i` in the array:  
     - Set `jumps[i]` to **infinity** initially, representing an unreachable state.  
     - Check all previous positions `j` to see if the current position can be reached from `j`.  
     - If yes, update `jumps[i]` to the minimum jumps required to reach `i`.  

4. **Return the Result:**  
   - Return the value in `jumps[n-1]`, which represents the minimum number of jumps required to reach the end of the array.  

## Program:
```
/*
To implement the program to finding the minimum number of jumps needed to reach end of the array.

Developed by: SHALINI K
Register Number: 212222240095
*/

def minJumps(arr, n):
    jumps = [0 for i in range(n)]
 
    if (n == 0) or (arr[0] == 0):
        return float('inf')
 
    jumps[0] = 0
    for i in range(1, n):
        jumps[i] = float('inf')
        for j in range(i):
            if (i <= j + arr[j]) and (jumps[j] != float('inf')):
                jumps[i] = min(jumps[i], jumps[j] + 1)
                break
    return jumps[n-1]
arr = []
n = int(input()) #len(arr)
for i in range(n):
    arr.append(int(input()))
print('Minimum number of jumps to reach','end is', minJumps(arr,n))
 
```

## Output:

![image](https://github.com/user-attachments/assets/84a64306-2bd9-46f8-86a8-e0f83422a6f6)


## Result:
Thus the program was executed successfully for finding the minimum number of jumps to reach end.
