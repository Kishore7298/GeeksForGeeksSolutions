##  Find distinct elements 
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
const int MAX = 1000;

int getCount(int a[][MAX], int n){
    unordered_set<int> val;
    for(int j=0;j<n;j++){
        val.insert(a[0][j]);
    }
    for(int i=1;i<n;i++){
        unordered_set<int> temp;
        for(int j=0;j<n;j++){
            temp.insert(a[i][j]);
        }
        //unordered_set<int> :: iterator itr;
        for(auto it=val.begin(); it!=val.end();){
            if(temp.find(*it) == temp.end()) it=val.erase(it);
            else it++;
        }
        if(val.size() == 0)
        {
            return 0;
        }
    }
    //unordered_set<int> :: iterator itr;
    //for(itr=val.begin();itr != val.end(); itr++){
    //    cout<< *itr <<" ";
    //}
    //cout<<endl;
    return val.size();
}

int main()
 {
	int test;
	int n;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>n;
	    int a[n][MAX];
	    for(int k=0;k<n;k++){
	        for(int j=0;j<n;j++){
	            cin>>a[k][j];
	        }
	    }
	    cout<<getCount(a,n)<<endl;
	    //getCount(a,n);
	}
	return 0;
}
```
