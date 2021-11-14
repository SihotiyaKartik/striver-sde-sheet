[Duplicate in array of N+1 integers](https://leetcode.com/problems/find-the-duplicate-number/)

```cpp

//using floyd's tortoise method
class Solution {
public:
    int findDuplicate(vector<int>& nums) {
        //concept of slow and fast, same as we do find duplicates in doubly linked list
        int slow = nums[0]; 
        int fast = nums[nums[0]];
        while(slow != fast){
            slow = nums[slow];
            fast = nums[nums[fast]];
        }
        
        //pointing fast to first element
        fast = 0;
        
        while(slow != fast){
            slow = nums[slow];
            fast = nums[fast];
        }
        return slow;
    }
};

```
