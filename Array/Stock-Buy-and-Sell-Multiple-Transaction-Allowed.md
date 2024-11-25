```cpp
class Solution {
  public:
    int maximumProfit(vector<int> &prices) {
        int prof=0, curr=prices[0];
        for(int i=1; i<prices.size(); i++) {
            if(prices[i]>=curr) {
                prof += (prices[i]-curr); 
            }
            curr = prices[i];
        }
        return prof;
    }
};
```
