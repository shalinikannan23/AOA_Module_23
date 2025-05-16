## DATE:
## AIM :
To find the maximum sum of a contiguous subarray within a one-dimensional integer array using Kadane's Algorithm.

## Algorithm

1. Initialize two variables:
   - `max_sum` to the first element of the array (to handle negative numbers)
   - `current_sum` to 0

2. Traverse each element `a[i]` in the array:
   - Add `a[i]` to `current_sum`
   - If `current_sum` becomes negative, reset it to 0 (start a new subarray)
   - Update `max_sum` if `current_sum` is greater than `max_sum`

3. After iterating through the array, `max_sum` holds the maximum contiguous subarray sum.

## PROGRAM
```
DEVELOPED BY : SHALINI K
REGISTER NUMBER : 212222240095

def maxSubArraySum(a, size):
    max_sum = a[0]
    current_sum = 0
    
    for i in range(size):
        current_sum += a[i]
        
        if current_sum < 0:
            current_sum = 0
        
        if current_sum > max_sum:
            max_sum = current_sum
    
    return max_sum

if __name__ == '__main__':
    n = int(input("Enter number of elements: "))
    a = []
    for _ in range(n):
        a.append(int(input()))
    
    print("Maximum contiguous sum is", maxSubArraySum(a, n))
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/cd47ce5f-decd-4d55-986f-5e88705e7e65)

## RESULT :
Thus, the program successfully calculates the maximum sum of a contiguous subarray using Kadane's algorithm.
