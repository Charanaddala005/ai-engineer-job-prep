python code:
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
    minimum_price = prices[i]
    max_profit  = 0
    for i in range(0, len(prices)):
            profit = prices[i] - minimum_price
            if prices[i] < minimum_price:
                 minimum_price = prices[i]
            if profit > max_profit:
                 max_profit = profit
     return max_profit

Algorithm:
firstly we assign two varibles such as minimum_price and max_profit
initially the value of max_profit will be 0 and vakue of minimum_price will be the first element in the array [i]
then while iterating in the for loop we assign the vakue of profit as the diff between prices[i] and minimum_price
then we iterate through the condition and return max_profit
            
            
