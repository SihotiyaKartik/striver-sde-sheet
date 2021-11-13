[Sort Colors](https://leetcode.com/problems/sort-colors/)

```cpp

class Solution {
public:
    void swap(int *a, int *b){
    int temp = *a;
    *a = *b;
    *b = temp;
    }
    
    void sortColors(vector<int>& nums) {
        int low=0,high=nums.size()-1,mid=0;
        //low for 0, mid for 1, high  for 2
        while(mid <= high){
            if(nums[mid]==0){
                swap(&nums[low++],&nums[mid++]);
            }
            else if(nums[mid]==1){
                mid++;
            }
            else {
                swap(&nums[mid],&nums[high--]);
            }
        }
    }
};

```
