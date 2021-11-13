[Stock Buy and Sell](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

```cpp

class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int min_price = prices[0];
        int max_profit = 0;
        for(int i=1;i<prices.size();i++){
            if(prices[i] > prices[i-1]){
                max_profit = max(max_profit,prices[i] - min_price);
            }
            else{
                min_price = min(min_price,prices[i]);
            }
        }
        return max_profit;
    }
};

```