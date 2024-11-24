### Brute Force
<br>

#### Steps
<br>

    1. Generate all possible permutations
    2. Linear Search to find given permutaion
    3. Next permutation is the result

<br>

    Time: O(N! * N)
    Space: O(N! * N)

<br>

---

### Optimal

<br>

    1. Time: O(NLogN)
    2. Space: O(1)

<br>

```cpp
class Solution {
public:
    void nextPermutation(vector<int>& nums) {
        int n = nums.size();
        int ind=-1;
        for(int i=n-1;i>=1;i--) {
            if(nums[i-1]<nums[i]) {
                ind=i-1;
                break;
            }
        }
        if(ind!=-1) {
            for(int i=n-1;i>ind;i--) {
                if(nums[ind]<nums[i]) {
                    swap(nums[ind], nums[i]);
                    break;
                }
            }
        }
        sort(nums.begin()+ind+1,nums.end());
    }
};
```
