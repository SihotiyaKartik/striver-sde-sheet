[N meeting in a room](https://practice.geeksforgeeks.org/problems/n-meetings-in-one-room-1587115620/1)

```cpp

class Solution
{
    public:
    //Function to find the maximum number of meetings that can
    //be performed in a meeting room.
    int maxMeetings(int start[], int end[], int n)
    {
        // Your code here
        vector<pair<int,int> > v;
        int count = 1;
        for(int i=0;i<n;i++){
            v.push_back(make_pair(end[i],start[i]));
        }
        sort(v.begin(),v.end());
        int prev =  v[0].first;
        for(int i=1;i<n;i++){
            if(v[i].second > prev){
                count++;
                prev = v[i].first;
            }
        }
        return count;
    }
};

```