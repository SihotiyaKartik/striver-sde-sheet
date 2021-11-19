[Majority element (>N/2 times)](https://leetcode.com/problems/majority-element/)

```cpp

class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int n  = nums.size();
        if(n==1)return nums[0];
        int temp = 1;
        
        sort(nums.begin(),nums.end());
        for(int i=1;i<n;i++){
            if(nums[i]==nums[i-1]){
                temp++;
                if(temp>=ceil((double)n/2))return nums[i];
            }
            else{
                temp=1;
            }
        }
        return -1;
    }
};

//another method
//Since the majority element appears more than n / 2 times, the n / 2-th element in the sorted nums must be the majority element.

class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int n  = nums.size();
        if(n==1)return nums[0];
        sort(nums.begin(),nums.end());
        return nums[n/2];
    }
};

```
