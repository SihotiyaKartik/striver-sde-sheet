[Longest Consequence Problem](https://leetcode.com/problems/longest-consecutive-sequence/)

```cpp

class Solution {
public:
    int longestConsecutive(vector<int>& nums){
        if(nums.size()==0)return 0;
        sort(nums.begin(),nums.end());
        int max_count = 0;
        int count = 1;
        for(int i=1;i<nums.size();i++){
            if(nums[i]==nums[i-1]+1){
                count++;
            }
            else if(nums[i]==nums[i-1]){
                continue;
            }
            else{
                max_count = max(max_count,count);
                count = 1;
            }
        }
        max_count = max(max_count,count);
        return max_count;
    }
};
```