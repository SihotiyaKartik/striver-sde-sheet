[Job Sequencing Problem](https://practice.geeksforgeeks.org/problems/job-sequencing-problem-1587115620/1#)

```cpp

// { Driver Code Starts
// Program to find the maximum profit job sequence from a given array 
// of jobs with deadlines and profits 
#include<bits/stdc++.h>
using namespace std; 

// A structure to represent a job 
struct Job 
{ 
    int id;	 // Job Id 
    int dead; // Deadline of job 
    int profit; // Profit if job is over before or on deadline 
}; 


 // } Driver Code Ends
/*
struct Job 
{ 
    int id;	 // Job Id 
    int dead; // Deadline of job 
    int profit; // Profit if job is over before or on deadline 
};
*/

class Solution 
{
    public:
    //Function to find the maximum profit and the number of jobs done.
    vector<int> JobScheduling(Job arr[], int n) 
    { 
        // your code here
        vector<pair<int,int>> a(n);
        for(int i=0;i<n;i++){
            a[i].first = arr[i].profit;
            a[i].second = arr[i].dead;
        }
        
        sort(a.begin(),a.end(),greater<>());
        vector<int> ans(101,0);
        for(int i=0;i<n;i++){
            for(int j=a[i].second-1;j>=0;j--){
                if(ans[j]==0){
                    ans[j] = a[i].first;
                    break;
                }
            }
        }
        int count = 0;
        for(int i=0;i<101;i++){
            if(ans[i])count++;
        }
        int sum = 0;
        sum = accumulate(ans.begin(),ans.end(),0);\
        return {count,sum};
        
    } 
};

```