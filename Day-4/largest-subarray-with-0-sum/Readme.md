[Largest subarray with 0 sum](https://practice.geeksforgeeks.org/problems/largest-subarray-with-0-sum/1)

```cpp


class Solution{
    public:
    int maxLen(vector<int>&A, int n)
    {   
        unordered_map<int,int> mp;
        int count = 0;
        int sum = 0;
        for(int i=0;i<n;i++){
            sum += A[i];
            if(sum==0){
                count = i+1;
            }
            else{
                if(mp.find(sum)!=mp.end()){
                    count = max(count,i-mp[sum]);
                }
                else{
                    mp[sum] = i;
                }
            }
        }
        return count;
        // Your code here
    }
};

```