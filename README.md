# AOA_Module_23
# EX 5A Minimum Cost Path
## DATE:
## AIM:
To write a Python program using A Naive recursive implementation of Minimum Cost Path Problem.




## Algorithm
1. Make a table to store minimum costs to reach each cell.
2. Set the starting cell's cost as the first cost.
3. Fill the first row and first column by adding costs from left and top.
4. For other cells, choose the smallest cost from left, top, or diagonal, and add the current cell's cost.
5. The last cell will have the minimum total cost to reach the end.

## Program:
```
/*
A program to implement to find the Minimum Cost Path Problem using a  Naive recursive Approach.

Developed by:  LOKESH RAHUL V V
Register Number: 212222100024
*/
```
```
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

## Output:
![image](https://github.com/user-attachments/assets/de355415-f4d7-4237-9af5-5d93d4835f38)




## Result:
Thus the above program was executed successfully for finding the minimum cost.
# EX 5B Coin Change Problem
## DATE:
## AIM:
To compute the fewest number of coins that we need to make up the amount given.


## Algorithm
1. If amount is 0, answer is 0; if coins are too big, answer is -1.
2. Make a list dp to remember the fewest coins needed for each amount.
3. Set 1 coin for amounts equal to the coin values.
4. For bigger amounts, check if using a coin gives fewer coins, and update.
5. At the end, return the answer from dp[amount]
## Program:
```
/*
Create a python function to compute the fewest number of coins that we need to make up the amount given.

.
Developed by:  LOKESH RAHUL V V
Register Number: 212222100024
*/
```
```
class Solution(object):
    def coinChange(self, coins, amount):
        if amount == 0 :
            return 0
        if min(coins) > amount:
            return -1
        dp = [-1 for i in range(0, amount + 1)]
        for i in coins:
            if i > len(dp) - 1:
                continue
            dp[i] = 1
            for j in range(i + 1, amount + 1):
                if dp[j - i] == -1:
                    continue
                elif dp[j] == -1:
                    dp[j] = dp[j - i] + 1
                else:
                    dp[j] = min(dp[j], dp[j - i] + 1)
        return dp[amount]
      
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))
print(ob1.coinChange(s,amt))
```

## Output:
![image](https://github.com/user-attachments/assets/9bb0c7ab-76b8-4441-969e-94f6fb0838d2)




## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
# EX 5C Kadane's Algorithm
## DATE:
## AIM:
To write a python program to find the maximum contiguous subarray.


## Algorithm
1. Start with the first element as the maximum (max_so_far) and set max_ending_here to 0.
2. Go through each element of the array one by one.
3. Add the current element to max_ending_here.
4. If max_ending_here becomes negative, reset it to 0; if it's greater than max_so_far, update max_so_far.
5. After checking all elements, return max_so_far as the biggest sum.

## Program:
```
/*
To implement the program to find the maximum contiguous subarray.


Developed by:  LOKESH RAHUL V V
Register Number: 212222100024
*/
```
```
def maxSubArraySum(a,size):
    max_so_far = a[0]
    max_ending_here = 0
    for i in range(0, size):
        max_ending_here = max_ending_here + a[i]
        if max_ending_here < 0:
            max_ending_here = 0
        elif (max_so_far < max_ending_here):
            max_so_far = max_ending_here
              
    return max_so_far
n=int(input())  
a =[] #[-2, -3, 4, -1, -2, 1, 5, -3]
for i in range(n):
    a.append(int(input()))
print("Maximum contiguous sum is", maxSubArraySum(a,n))
```

## Output:
![image](https://github.com/user-attachments/assets/5eb49e77-c9a9-4b15-a9b2-ae67b948ab3c)




## Result:
Thus the program was executed successfully for finding the maximum contiguous sum of subarray..
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


Developed by:  LOKESH RAHUL V V
Register Number: 212222100024
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
