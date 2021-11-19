[2 Sum Problem](https://leetcode.com/problems/two-sum/)

```cpp

class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> v;
        unordered_map<int,std::size_t> temp;
        for(int i=0;i<nums.size();i++){
            if(temp.count(target-nums[i])){
                v.push_back(temp[target-nums[i]]);
                v.push_back(i);
                return v;
            }
            temp[nums[i]] = i;
        }
        return v;
    }
};

```