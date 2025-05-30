# EX 5D Minimum Jump to Reach End Array
## DATE:
## AIM:
To write a python program for finding the minimum number of jumps needed to reach end of the array using Dynamic Programming.


## Algorithm
1. If the first element is 0 or the array is empty, return infinity because you can't move.
2. Create an array jumps where each element represents the minimum jumps needed to reach that position.
3. For each position, check if you can jump from any previous position that can reach it and update the jumps accordingly.
4. For each valid jump, keep track of the minimum jumps needed.
5. Return the minimum number of jumps to reach the last position. 

## Program:
```
/*
To implement the program to finding the minimum number of jumps needed to reach end of the array.


Developed by: ASHWIN KUMAR S
Register Number: 212222240013
*/
```
```
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
![Screenshot 2025-04-29 003905](https://github.com/user-attachments/assets/8d96c65f-252a-4230-93b3-c40d843955fc)






## Result:
Thus the program was executed successfully for finding the minimum number of jumps to reach end.
