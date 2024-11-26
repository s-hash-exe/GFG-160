```cpp
class Solution {
  public:
    int maximumProfit(vector<int> &prices) {
        int mxProf=0, buy=prices[0], sell=-1;
        for(int i=1; i<prices.size(); i++) {
            if(prices[i] <= buy) {
                buy=prices[i];
                //cout<<"Buying at "<<buy<<"\n";
            }
            else {
                sell=prices[i];
                //cout<<"Selling at " <<sell<<" for buy at "<<buy<<"\n";
                mxProf=max(mxProf,sell-buy);
            }
        }
        return mxProf;
    }
};
```
