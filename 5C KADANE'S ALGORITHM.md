# EX 5C Kadane's Algorithm
## DATE:
## AIM:
To write a python program to find the maximum contiguous subarray.


## Algorithm:

1. **Initialize Tracking Variables:**  
   - Set `max_till_now` to the first element of the array (to handle all-negative arrays).  
   - Set `max_ending` to `0` to track the sum of the current subarray.  

2. **Iterate Through the Array:**  
   - For each element in the array, add it to `max_ending`.  

3. **Reset for Negative Sums:**  
   - If `max_ending` becomes negative, reset it to `0` (this effectively starts a new subarray).  

4. **Update the Maximum Sum:**  
   - If the current `max_ending` is greater than `max_till_now`, update `max_till_now` to this new maximum.  

5. **Return the Result:**  
   - After the loop, return `max_till_now` as the maximum contiguous subarray sum. 

## Program:
```
/*
To implement the program to find the maximum contiguous subarray.

Developed by: SHALINI K 
Register Number: 212222240095
*/

def maxSubArraySum(a,size):
    max_till_now = a[0]
    max_ending = 0
    
    for i in range(0, size):
        max_ending = max_ending + a[i]
        if max_ending < 0:
            max_ending = 0
        
        
        elif (max_till_now < max_ending):
            max_till_now = max_ending
            
    return max_till_now
n=int(input())  
a =[] #[-2, -3, 4, -1, -2, 1, 5, -3]
for i in range(n):
    a.append(int(input()))
  
print("Maximum contiguous sum is", maxSubArraySum(a,n))
```

## Output:

![image](https://github.com/user-attachments/assets/d1f68239-2b5e-42b7-bbe1-28ec1834e5a2)


## Result:
Thus the program was executed successfully for finding the maximum contiguous sum of subarray..
