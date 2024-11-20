### Brute Force
<br>

    Time: O(N)
    Space: O(N)

<br>

```cpp
class Solution {
  public:
    void reverseArray(vector<int> &arr) {
        vector<int> rArr;
        for(int i=arr.size()-1; i>=0; i--) rArr.push_back(arr[i]);
        arr = rArr;
    }
};
```

<br>

---

<br>

### Optimal 
<br>

    Time: O(N)
    Space: O(1)

<br>

```cpp
class Solution {
  public:
    void reverseArray(vector<int> &arr) {
        int i=0, j=arr.size()-1;
        while(i<j) swap(arr[i++], arr[j--]);
    }
};
```
