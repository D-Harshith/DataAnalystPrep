Problem Name: Best Time to Buy and Sell Stock

Problem Number: LeetCode #121

Category: Array

Difficulty: Easy

Problem Description: Give a array you want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Solution Logic: Take the first value as the smallest value and if any other value is less than that it would become the new buy price else find the max profit by max(maxp, prices[i]-buy).

Code:
```python
def maxProfit(self, prices):
    buy = prices[0]
    maxp = 0
    for i in range(1, len(prices)):
        if prices[i] < buy:
            buy = prices[i]
        else:
            maxp = max(maxp, prices[i]-buy)
    return maxp

Last visited: 4/30/25