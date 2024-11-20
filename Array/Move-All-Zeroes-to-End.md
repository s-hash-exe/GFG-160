### Brute Force

<br>

    Time: O(N)
    Space: O(N)

<br>

```cpp
class Solution {
  public:
    void pushZerosToEnd(vector<int>& arr) {
        int countZ=0, ind=0;
        vector<int> nonZ;
        for(int i:arr) {
            if(i!=0) nonZ.push_back(i);
        }
        for(int i:nonZ) {
            arr[ind++]=i;
        }
        for(int i=ind; i<arr.size(); i++) {
            arr[i]=0;
        }
    }
};
```

<br>

---

<br>

### Optimal Approach

<br>

    Time: O(N)
    Space: O(1)

<br>

```cpp
class Solution {
  public:
    void pushZerosToEnd(vector<int>& arr) {
        int n=arr.size(), countZ=0, pz=0, pnz=0;
        while(pnz<n && pz<n) {
            while(pz<n && arr[pz]!=0) pz++;
            while(pnz<n && arr[pnz]==0) pnz++;
            if(pz<n && pnz<n) {
                if(pz<pnz) {
                    swap(arr[pz],arr[pnz]);
                }
                else {
                    pnz++;
                }
            }
        }
    }
};
```

<br>

```cpp
class Solution {
  public:
    void pushZerosToEnd(vector<int>& arr) {
        int j=-1;
        for(int i=0; i<arr.size(); i++) {
            if(arr[i]==0) {
                j=i;
                break;
            }
        }
        for(int i=j+1; i<arr.size(); i++) {
            if(arr[i]!=0 && j<arr.size()) {
                swap(arr[i], arr[j]);
                j++;
            }
        }
    }
};
```
