[Reverse pairs]()

```cpp

class Solution {
public:
    int count = 0;
    
    void merge(vector<int> &nums, int low, int mid, int high){
        
        int l=low,j = mid + 1;
        while(l<=mid && j<=high){
            if((long)nums[l] > (long)2*nums[j]){
                count += (mid-l+1);
                j++;
            }
            else{
                l++;
            }
        }
        sort(nums.begin() + low,nums.begin() + high + 1);
        
        
    }
    
    void mergesort(vector<int>& nums, int low, int high){
            if (low>=high) return;          
            int mid = low + (high-low)/2;
            mergesort(nums,low,mid);
            mergesort(nums,mid+1,high);
            merge(nums,low,mid,high);
            
        
    }
    
    int reversePairs(vector<int>& nums) {
        int n = nums.size();
        if(n<=1)return 0;
        mergesort(nums,0,n-1);
        return count;
        
    }
};

```