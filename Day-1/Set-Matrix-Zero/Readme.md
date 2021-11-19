[Set Matrix Zero](https://leetcode.com/problems/set-matrix-zeroes/)

```cpp
class Solution{

public:

void setZeros(vector<vector<int>>& matrix){
    int m = matrix.size();//rows
    int n = matrix[0].size();//columns
    bool flag = false;//for checking first column 

    //checking first columnn, if 0 exist
    for(int i=0;i<m;i++){
        if(matrix[i][0]==0)flag = true;
        for(int j=1;j<n;j++){
            if(matrix[i][j]==0){

                matrix[i][0] = 0;//setting first element of row as 0
                matrix[0][j] = 0;//setting first element of column as 0
            
            }
        }
    }

    //checking all rows&columns except first one
    for(int i=1;i<m;i++){
        for(int j=1;j<n;j++){
            if(matrix[i][0]==0 || matrix[0][j]==0)matrix[i][j] = 0;
        }
    }
    
    //if first element of matrix is 0, change all element of first row to 0
    if(matrix[0][0] == 0){
        for(int j=0;j<n;j++){
            matrix[0][j] = 0;
        }
    }

    //if flag is true change all element of first column to 0
    if(flag){
        for(int i=0;i<m;i++){
            matrix[i][0] = 0;
        }
    }   
}

};

```