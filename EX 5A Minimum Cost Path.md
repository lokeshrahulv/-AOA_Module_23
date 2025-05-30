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

Developed by: ASHWIN KUMAR S
Register Number: 212222240013
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
