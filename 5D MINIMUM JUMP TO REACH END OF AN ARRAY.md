## DATE :
## Aim
To find the minimum number of jumps needed to reach the end of the array from the start, where each element in the array represents the maximum jump length at that position, using Dynamic Programming.

## Algorithm

1. Initialize a list `jumps` of size `n` where `jumps[i]` will hold the minimum number of jumps needed to reach position `i`.

2. Set `jumps[0] = 0` since the start position requires zero jumps.

3. For each position `i` from 1 to `n-1`, do:
   - Initialize `jumps[i]` to infinity (or a very large number).
   - For each position `j` before `i` (from 0 to `i-1`), check if position `i` is reachable from position `j`:
     - If `i <= j + arr[j]` and `jumps[j]` is not infinity, update:
       ```
       jumps[i] = min(jumps[i], jumps[j] + 1)
       ```
     - Break early if a valid jump is found to optimize.

4. The value `jumps[n-1]` will contain the minimum number of jumps needed to reach the end.

## Program :
```
DEVELOPED BY : SHALINI K
REGISTER NUMBER : 212222240095

def minJumps(arr, n):
    jumps = [0] * n
    
    if n == 0 or arr[0] == 0:
        return float('inf')
    
    jumps[0] = 0
    
    for i in range(1, n):
        jumps[i] = float('inf')
        for j in range(i):
            if i <= j + arr[j] and jumps[j] != float('inf'):
                jumps[i] = min(jumps[i], jumps[j] + 1)
                break
    
    return jumps[n-1]

if __name__ == '__main__':
    n = int(input("Enter number of elements: "))
    arr = []
    for _ in range(n):
        arr.append(int(input()))
    
    result = minJumps(arr, n)
    if result == float('inf'):
        print("Cannot reach the end of the array.")
    else:
        print("Minimum number of jumps to reach end is", result)
```

## Output :
![image](https://github.com/user-attachments/assets/ed3ea20b-4e69-4784-840b-8163d9373deb)

## Result:
Thus, the program successfully computes the minimum number of jumps needed to reach the end of the array using dynamic programming.
