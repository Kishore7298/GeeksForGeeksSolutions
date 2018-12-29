## Boolean Matrix problem
Given a boolean matrix mat[M][N] of size M X N, modify it such that if a matrix cell mat[i][j] is 1 (or true) then make all the cells of ith row and jth column as 1.

#### Input:
The first line of input contains an integer T denoting the number of test cases.
The first line of each test case is r and c, r is the number of rows and c is the number of columns.
The second line of each test case contains all the elements of the matrix in a single line separated by a single space.

#### Output:
Print the modified array.
```
Constraints:
1 ≤ T ≤ 102
1 ≤ r, c ≤ 103
0 ≤ A[i][j] ≤ 1

Example:
Input:
3
2 2
1 0
0 0
2 3
0 0 0 
0 0 1
3 4
1 0 0
1 0 0
1 0 0
0 0 0

Output:
1 1
1 0
0 0 1 
1 1 1
1 1 1 1 
1 1 1 1 
1 0 1 1

Explanation:
Testcase1: Since only rist element of matrix has 1 (at index 1,1) as value, 
so first row and first column are modified to 1.
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;
const int MAX=1000;

void printBooleanMatrix(int a[][MAX], int m, int n){
    int row[m] ={0};
    int col[n] ={0};
    for(int i=0;i<m;i++){
        for(int j=0;j<n;j++){
            if(a[i][j] == 1){
                row[i]=1;
                col[j]=1;
            }
        }
    }
    for(int i=0;i<m;i++){
        for(int j=0;j<n;j++){
            if(row[i] ==1 || col[j] == 1){
                a[i][j]=1;
            }
        }
    }
    for(int i=0;i<m;i++){
        for(int j=0;j<n;j++){
            cout<<a[i][j]<<" ";
        }
        cout<<endl;
    }
}

int main()
 {
	int test;
	int n,m;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>m>>n;
	    int a[m][MAX];
	    for(int i=0;i<m;i++){
	        for(int k=0;k<n;k++){
	            cin>>a[i][k];
	        }
	    }
	    printBooleanMatrix(a,m,n);
	}
	return 0;
}
```
