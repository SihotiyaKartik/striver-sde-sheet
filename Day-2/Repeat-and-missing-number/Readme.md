[Repeat and Missing number](https://www.interviewbit.com/problems/repeat-and-missing-number-array/)

```cpp
vector<int> Solution::repeatedNumber(const vector<int> &A) {
    int n = A.size();
    vector<int> res(2);
    vector<int> temp(n+1,0);
    for(int i=0;i<n;i++){
        temp[A[i]]++;
    }
    for(int i=0;i<temp.size();i++){
        if(temp[i]>1)res[0] = i;
        if(temp[i]==0)res[1] = i;
    }
    return res;
}

```