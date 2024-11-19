### Brute Force

      1. Sort the array in descending order
      2. Find the second largest element
<br>

```cpp
// User function template for C++
class Solution {
  public:
    // Function returns the second
    // largest elements
    int getSecondLargest(vector<int> &arr) {
        sort(arr.begin(), arr.end(), greater<int>());
        for(int i:arr) {
            if(i!=arr[0]) {
                return i;
            }
        }
        return -1;
    }
};
```
<br>

    Time: O(NlogN + N) = O(NlogN)
    Space: O(1)

<br>

---

<br>

### Better

    1. Find the largest in 1st pass
    2. Find the second largest in 2nd pass.

<br>

```cpp
class Solution {
  public:
    // Function returns the second
    // largest elements
    int getSecondLargest(vector<int> &arr) {
        int max=INT_MIN, smax=INT_MIN;
        for(int num:arr) {
            if(num > max) max = num;
        }
        for(int num:arr) {
            if(num<max && num>smax) smax=num;
        }
        return (smax==INT_MIN)?-1:smax;
    }
};
```
<br>

    Time: O(N+N) = O(N)
    Space: O(1)

<br>

---

<br>

### Optimal

    1. Find the second largest along with largest in only one pass.
    
<br>

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

<br>

