## DATE:
## AIM :
To find the total number of distinct ways to get a change of `target` amount from an unlimited supply of coins in set `S` using Dynamic Programming.

## ALGORITHM :
1. **Input**:  
   - Coin denominations array `S = {S0, S1, ..., Sn-1}`  
   - Target amount `target`  
   - Number of coin types `n` (length of `S`)

2. **Base Cases**:  
   - If `target == 0`: return 1 (there is one way to make zero amount)  
   - If `target < 0` or `n < 0`: return 0 (no way to make change)

3. **Recursive Steps**:  
   For the coin at index `n`, two choices:  
   - **Include** the coin: reduce target by `S[n]` and keep `n` (unlimited usage)  
   - **Exclude** the coin: reduce `n` by 1 to move to next coin, keep target same

4. **Combine**:  
   Total ways = ways including coin + ways excluding coin.

5. **Output**:  
Call `count(S, n-1, target)` to get the total number of ways.

## PROGRAM :
```
DEVELOPED BY: SHALINI K
REGISTER NUMBER: 212222240095

def count(S, n, target):
    if target==0:
        return 1
    if target<0 or n<0:
        return 0
    incl=count(S,n,target-S[n])
    excl=count(S,n-1,target)
    return incl+excl

if __name__ == '__main__':
    S = []#[1, 2, 3]
    n=int(input())
    target = int(input())
    for i in range(n):
        S.append(int(input()))
    print('The total number of ways to get the desired change is',
        count(S, len(S) - 1, target))
```

## OUTPUT :
![image](https://github.com/user-attachments/assets/6411ba3f-eaa8-439f-902f-f0bfeb4ac481)

## RESULT :
Thus, the program successfully computes the total number of distinct ways to make change for the given target amount using the provided coin denominations.
