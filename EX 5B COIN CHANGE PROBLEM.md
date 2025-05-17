# EX 5B Coin Change Problem
## DATE:
## AIM:
To compute the fewest number of coins that we need to make up the amount given.


## Algorithm:

1. **Initialize the DP Array:**  
   - Create a `dp` array of size `(amount + 1)` initialized to **infinity** (representing unreachable amounts).  
   - Set `dp[0]` to `0`, as zero coins are needed to make a total of 0.  

2. **Fill the DP Array:**  
   - For each coin in the list, update the `dp` values for all possible amounts from the coin's value to the target amount.  
   - Use the relation: `dp[i] = min(dp[i], dp[i - coin] + 1)`
3. If the final entry in the `dp` array (`dp[amount]`) is still infinity, return -1 to indicate that the amount cannot be formed.
4. Otherwise, return the value at `dp[amount]`, representing the minimum number of coins required.
   

## Program:
```
/*
Create a python function to compute the fewest number of coins that we need to make up the amount given.

Developed by: SHALINI K
Register Number: 212222240095
*/

class Solution(object):
   def coinChange(self, coins, amount):
       dp = [float('inf')] * (amount + 1)
       dp[0]=0
       for coin in coins:
           for i in range(coin, amount + 1):
               dp[i] = min(dp[i], dp[i - coin] + 1)
       return dp[amount] if dp[amount]!=float('inf') else -1
      
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))

print(ob1.coinChange(s,amt))
```

## Output:

![image](https://github.com/user-attachments/assets/6f115770-0bcf-497d-a6b9-a87da8415d2d)


## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
