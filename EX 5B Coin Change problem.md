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
Developed by: ASHWIN KUMAR S
Register Number: 212222240013
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
