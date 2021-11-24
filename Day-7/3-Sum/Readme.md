[3 Sum](https://leetcode.com/problems/3sum/)

```cpp

class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        int n = nums.size();
        vector<vector<int>> res;
        if(n==0)return res;
        sort(nums.begin(),nums.end());
        for(int i=0;i<n;i++){
            if(nums[i]>0)break;
            
            if(i>0 && nums[i]==nums[i-1])continue;
            
            int l=i+1,r=n-1;
            while(l<r){
                int sum = nums[i]+nums[l]+nums[r];
                if(sum < 0)++l;
                else if(sum > 0)--r;
                else{
                    res.push_back({nums[i],nums[l],nums[r]});
                    int left = nums[l],right=nums[r];
                    while (l < r && nums[l] == left) ++l;
				    while (l < r && nums[r] == right) --r;
                    
                }
            }
        }
        return res;
    
    }
};

```