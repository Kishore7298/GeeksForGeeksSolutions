##  Smallest Positive missing number 
You are given an unsorted array with both positive and negative elements. You have to find the smallest positive number missing from the array in O(n) time using constant extra space.

#### Input:
First line consists of T test cases. First line of every test case consists of N, denoting the number of elements in array. Second line of every test case consists of elements in array.

#### Output:
Single line output, print the smallest positive number missing.
```
Constraints:
1<=T<=100
1<=N<=100

Example:
Input:
2
5
1 2 3 4 5
5
0 -10 1 3 -20
Output:
6
2
```
#### Solution:
```c++
#include<iostream>
#include <bits/stdc++.h>
using namespace std;

int seggregate(int a[],int n){
    int j=0;
    for(int i=0;i<n;i++){
        if(a[i]<=0){
           swap(a[i],a[j]) ;
           j++;
        }
    }
    return j;
}

int getMissing(int a[],int n){
    for(int i=0;i<n;i++){
        if(abs(a[i])-1<n && a[abs(a[i])-1]>0){
            a[abs(a[i])-1] = -a[abs(a[i])-1];
        }
    }
    for(int i=0;i<n;i++){
        if(a[i]>0){
            return i+1;
        }
    }
    return n+1;
}

int findMissing(int a[],int n){
    int index = seggregate(a,n);
    
    return getMissing(a+index,n-index);
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
	    cout<<findMissing(a,n)<<endl;
	}
	return 0;
}
```
