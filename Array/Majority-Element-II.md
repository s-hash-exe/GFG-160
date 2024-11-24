#### Note
<br>

    At max 2 elements can have a frquency greater then n/3.

<br>

---

### Brute Force
<br>

    Time: O(N)
    Space: O(N)

<br>

```cpp
class Solution {
  public:
    // Function to find the majority elements in the array
    vector<int> findMajority(vector<int>& arr) {
        int n = arr.size();
        vector<int> ans;
        unordered_map<int,int> mp;
        for(int i:arr) mp[i]++;
        for(auto it:mp) {
            if(it.second > (n/3)) ans.push_back(it.first);
        }
        sort(ans.begin(), ans.end());
        return ans;
    }
};
```

<br>

---

<br>

### Optimal

      Time: O(N)
      Space: O(1)

<br>

```cpp
class Solution {
  public:
    // Function to find the majority elements in the array
    vector<int> findMajority(vector<int>& arr) {
        vector<int> ans;
        int minFreq = arr.size()/3 +1;
        int num1=INT_MIN, c1=0, num2=INT_MIN, c2=0;
        for(int num:arr) {
            if(c1==0 && num!=num2) {
                num1=num;
                c1=1;
            }
            else if(c2==0 && num!=num1) {
                num2=num;
                c2=1;
            }
            else if(num==num1) c1++;
            else if(num==num2) c2++;
            else {
                c1--;
                c2--;
            }
        }
        c1=0, c2=0;
        for(int num:arr) {
            if(num==num1) c1++;
            else if(num==num2) c2++;
        }
        if(c1>=minFreq) ans.push_back(num1);
        if(c2>=minFreq) ans.push_back(num2);
        sort(ans.begin(), ans.end());
        return ans;
    }
};
```
    
