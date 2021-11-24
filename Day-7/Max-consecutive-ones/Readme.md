[Max Consecutive ones](https://leetcode.com/problems/max-consecutive-ones/)

```cpp

class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int n = nums.size();
        int count = 0;
        int Max = 0;
        for(int i=0;i<n;i++){
            if(nums[i]==1){
                count++;
            }
            else{
                Max = max(Max,count);
                count = 0;
            }
        }
        Max = max(Max,count);
        return Max;
    }
};

```