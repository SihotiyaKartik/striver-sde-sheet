[Fractional Knapsack](https://practice.geeksforgeeks.org/problems/fractional-knapsack-1587115620/1#)

```cpp

// { Driver Code Starts
#include <bits/stdc++.h>
using namespace std;

struct Item{
    int value;
    int weight;
};


 // } Driver Code Ends
//class implemented
/*
struct Item{
    int value;
    int weight;
};
*/


class Solution
{
    
    
    public:
    //Function to get the maximum total value in the knapsack.
    static bool comp(Item a, Item b){
        double p = (double)a.value / (double)a.weight;
        double q = (double)b.value / (double)b.weight;
        return p > q;
    }
    
    double fractionalKnapsack(int W, Item arr[], int n)
    {
        // Your code here
        sort(arr,arr+n,comp);
        int w = 0;
        double v = 0.0;
        for(int i=0;i<n;i++){
            if(w + arr[i].weight <= W){
                w += arr[i].weight;
                v += arr[i].value;
                
                
            }
            
            else{
                int remain = W - w;
                v += (arr[i].value/(double)arr[i].weight)*(double)remain;
                break;
            }
        }
        return v;
        
        
    }
        
};

```