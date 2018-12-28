##  Transpose of Matrix 
Write a program to find transpose of a square matrix of size N. Transpose of a matrix is obtained by changing rows to columns and columns to rows.

#### Input:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case contains an integer n denoting the size of the square matrix. Then in the next line are N*N space separated values of the matrix.

#### Output:
For each test case output will be the space separated values of the transpose of the matrix
 
```
Constraints:
1<=T<=1000
1<=N<=20

Example:
Input:
2
4
1 1 1 1 2 2 2 2 3 3 3 3 4 4 4 4
2
1 2 -9 -2 
 

Output:
1 2 3 4 1 2 3 4 1 2 3 4 1 2 3 4
1 -9 2 -2 
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;
const int MAX =20;

void printTranspose(int a[][MAX], int n){
    int b[n][n];
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            b[i][j] = a[j][i];
        }
    }
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            cout<<b[i][j]<<" ";
        }
    }
}

int main()
 {
	int test;
	int n;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>n;
	    int a[n][MAX];
	    for(int i=0;i<n;i++){
	        for(int k=0;k<n;k++){
	            cin>>a[i][k];
	        }
	    }
	    printTranspose(a,n);
	    cout<<endl;
	}
	return 0;
}
```
