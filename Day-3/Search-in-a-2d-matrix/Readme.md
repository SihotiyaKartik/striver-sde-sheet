[Serach in a 2D matrix]()

```cpp

//logic is treat 2D array as a list of sorted array with m*n elements and apply binary search

class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int m = matrix.size();
        int n = matrix[0].size();
        int low = 0;
        int high = m*n -1;
        while(low <= high){
            int mid = low + (high - low )/2;
            int mid_v = matrix[mid/n][mid%n];
            if(mid_v == target){
                return true;
            }
            else if(mid_v > target){
                high = mid-1;
            }
            else{
                low = mid+1;
            }
        }
        return false;
        
        
    }
};

```