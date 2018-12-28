##  Spirally traversing a matrix 
Given a 2D matrix of size M*N. Traverse and print the matrix in spiral form.

#### Input:
The first line of the input contains a single integer T, denoting the number of test cases. Then T test cases follow. Each testcase has 2 lines. First line contains M and N respectively separated by a space. Second line contains M*N values separated by spaces.

#### Output:
Elements when travelled in Spiral form, will be displayed in a single line.
```
Constraints:
1 <=T<= 100
2 <= M, N <= 10
0 <= Ai <= 100

Example:
Input:
1
4 4
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16
Output:
1 2 3 4 8 12 16 15 14 13 9 5 6 7 11 10
```
##### Explanation:
Testcase 1: Refer this.    
    ![alt text](https://www.cdn.geeksforgeeks.org/wp-content/uploads/spiral-matrix.png)
    
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;
const int MAX = 15;

void spiralPrint(int a[][MAX], int m, int n){
    int l=0,k=0;
    while(k<m&&l<n){
        for(int i=l;i<n;i++){
            cout<<a[k][i]<<" ";
        }
        k++;
        for(int i=k;i<m;i++){
            cout<<a[i][n-1]<<" ";
        }
        n--;
        if(k<m){
            for(int i=n-1;i>=l;i--){
                cout<<a[m-1][i]<<" ";
            }
            m--;
        }
        if(l<n){
            for(int i=m-1;i>=k;i--){
                cout<<a[i][l]<<" ";
            }
            l++;
        }
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
	    spiralPrint(a,m,n);
	    cout<<endl;
	}
	return 0;
}
```
