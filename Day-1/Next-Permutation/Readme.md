[Next-Permutation](https://leetcode.com/problems/next-permutation/)

```cpp

class Solution{
public:

//function for swaping two numbers
void swap(int *a, int *b){
    int temp = *a;
    *a = *b;
    *b = temp;
}

//function for reversing subarray
void reverse(vector<int>& nums, int n){
    int i = n;
    int j = nums.size()-1;
    while(i<j){
        swap(&nums[i],&nums[j]);
        i++;
        j--;
    }
}

void nextPermutation(vector<int>& nums){
    int l = nums.size() - 2;//points last second element of array

    //finding a pair from right in which nums[l]<=nums[l+1]
    while(l>=0 && nums[l+1]<=nums[l])l--;
    if(l>=0){
        int k = nums.size()-1;
        while(nums[k] <= nums[l])k--;
        swap(&nums[l],&nums[k]);//swaping nums[l] with a number which is just larger than nums[l]
    }
    reverse(nums,l+1);//reversing subarray after lth index to get next lexographical permutation

}


};


```