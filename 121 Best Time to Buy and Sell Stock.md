## 121 Best Time to Buy and Sell Stock

```c++
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        if(prices.size() < 2) return 0;
        int low = prices[0], profit = 0;
        for(auto num: prices) {
            low = min(low, num);
            profit = max(num - low, profit);
        }
        return profit;
    }
};
```

