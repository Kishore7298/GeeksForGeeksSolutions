## Find distinct elements 
Given a N x N matrix. Write a program to find count of all the distinct elements common to all rows of the matrix. Print count of such elements.

#### Input:
First line of input contains a single integer T which denotes the number of test cases. T test cases follows. First line of each test case contains a single integer N which denotes the dimension of matrix. Second line of each test case contains N*N space separated integers which denotes elements of the matrix.

#### Output:
For each test case, print count of all the distinct elements common to all rows of the matrix.
```
Constraints:
1 <= T <= 100
1 <= N <= 1000

Example:
Input:
2
4
2 1 4 3 1 2 3 2 3 6 2 3 5 2 5 3
5
12 1 14 3 16 14 2 1 3 35 14 1 14 3 11 14 25 3 2 1 1 18 3 21 14

Output:
2
3
```
#### Solution:
```c++
#include<iostream>
#include<bits/stdc++.h>
using namespace std;

bool isSubarray(int a[], int b[], int m, int n){
    unordered_set<int> big;
    unordered_set<int> small;
    for(int i=0;i<m;i++){
        big.insert(a[i]);
    }
    for(int i=0;i<n;i++){
        small.insert(b[i]);
    }
    for(auto itr= small.begin(); itr != small.end(); itr++){
        if(big.find(*itr) == big.end()){
            return false;
        }
    }
    return true;
}

int main()
 {
	int test;
	int n,m;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>m>>n;
	    int a[m],b[n];
	    for(int j=0;j<m;j++)
	        cin>>a[j];
	     for(int k=0;k<n;k++)
	        cin>>b[k];
	    if(isSubarray(a,b,m,n)){
	        cout<<"Yes"<<endl;
	    } else {
	        cout<<"No"<<endl;
	    }
	}
	return 0;
}
```
