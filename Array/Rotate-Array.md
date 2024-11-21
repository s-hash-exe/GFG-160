### Brute Force
<br>

    Time: O(N)
    Space: O(N)

<br>

```cpp
class Solution {
  public:

    // Function to rotate an array by d elements in counter-clockwise direction.
    void rotateArr(vector<int>& arr, int d) {
        d = d%arr.size();
        vector<int> temp;
        for(int i=0; i<d; i++) temp.push_back(arr[i]);
        for(int i=d; i<arr.size(); i++) arr[i-d]=arr[i];
        for(int i=arr.size()-d; i<arr.size(); i++) arr[i]=temp[i-(arr.size()-d)];
    }
};
```

<br>

---

<br>

### Optimal Solution
<br>

    Time: O(N)
    Space: O(1)

<br>

```cpp
class Solution {
  private:
    void reverse(vector<int> &arr, int start, int end) {
        while(start<end) swap(arr[start++], arr[end--]);
    }
  public:
    // Function to rotate an array by d elements in counter-clockwise direction.
    void rotateArr(vector<int>& arr, int d) {
        d = d%arr.size();
        reverse(arr,0,d-1);
        reverse(arr,d,arr.size()-1);
        reverse(arr,0,arr.size()-1);
    }
};
```
