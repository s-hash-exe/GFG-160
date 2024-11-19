```cpp
class Solution {
  public:
    // Function returns the second
    // largest elements
    int getSecondLargest(vector<int> &arr) {
        int max=INT_MIN, smax=INT_MIN;
        for(int num:arr) {
            if(num > max) {
                smax = max;
                max = num;
            }
            else if(num>smax && num<max) {
                smax = num;
            }
        }
        return (smax==INT_MIN)?-1:smax;
    }
};
```

<br>

    Time: O(N)
    Space: O(1)
