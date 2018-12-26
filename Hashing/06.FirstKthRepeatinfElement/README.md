##  First element to occur k times 
Given an array of N integers. The task is to find the first element that occurs K number of times. If no element occurs K times the print -1.

#### Input:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. The first line of each test case contains an integer N denoting the size of an array and the number K. The second line of each test case contains N space separated integers denoting elements of the array A[ ].

#### Output:
For each test case in a new line print the required answer.
```
Constraints:
1 <= T <= 100
1 <= N, K <= 105
1<= A <= 106

Example:
Input :
1
7 2
1 7 4 3 4 8 7
Output :
7

Explanation:
Both 7 and 4 occur 2 times. But 7 is the first that occurs 2 times.
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

int repeatingElement(int a[],int n,int k){
    unordered_map<int,int> hash;
    for(int i=0;i<n;i++){
        hash[a[i]]=0;
    }
    for(int i=0;i<n;i++){
        hash[a[i]]++;
    }
    for(int i=0;i<n;i++){
        if(hash[a[i]] == k)
        return a[i];
    }
    //for(auto itr=hash.begin(); itr != hash.end();itr++){
    //    cout<<itr->first<<" "<<itr->second;
    //}
    return -1;
}

int main()
 {
	int test;
	int n,k;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>n>>k;
	    int a[n];
	    for(int j=0;j<n;j++){
	        cin>>a[j];
	    }
	    cout<<repeatingElement(a,n,k)<<endl;
	    
	}
	return 0;
}
```
