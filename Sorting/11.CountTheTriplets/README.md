##  Count the triplets 
Given an array of distinct integers. The task is to count all the triplets such that sum of two elements equals the third element.

#### Input:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case consists of two lines. First line of each test case contains an Integer N denoting size of array and the second line contains N space separated elements.

#### Output:
For each test case, print the count of all triplets, in new line. If no such triplets can form, print "-1".
```
Constraints:
1<=T<=100
3<=N<=105
1<=A[i]<=106

Example:
Input:
2
4
1 5 3 2
3
3 2 7
Output:
2
-1
```
#### Solution:
```c++
#include<iostream>
#include<bits/stdc++.h>
using namespace std;

int getTriplet(int a[],int n){
    int result = 0;
    sort(a,a+n);
    for(int i=n-1;i>=0;i--){
        int j=0;
        int k=i-1;
        while(j<k){
            if(a[i] ==a[j]+a[k]){
                result++;
                j++;
                k--;
            }
            if(a[i] >a[j]+a[k])
                j++;
            if(a[i]<a[j]+a[k])
                k--;
        }
    }
    return result;
    //for(int i=0;i<n;i++){
    //    cout<<a[i]<<" ";
    //}
    //cout<<endl;
}

int main()
 {
	int test;
	int n;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>n;
	    int a[n];
	    for(int j=0;j<n;j++){
	        cin>>a[j];
	    }
	   int res = getTriplet(a,n);
	   if(res !=0)
	    cout<<res<<endl;
	   else
	    cout<<-1<<endl;
	}
	return 0;
}
```
