## Count pairs from two sorted matrices with given sum
 Given two sorted matrices mat1 and mat2 of size n x n of distinct elements. Given a value x. The problem is to count all pairs from both matrices whose sum is equal to x.
Note: The pair has an element from each matrix. Matrices are strictly sorted which means that matrices are sorted in a way such that all elements in a row are sorted in increasing order and for row ‘i’, where 1 <= i <= n-1, first element of row 'i' is greater than the last element of row 'i-1'.
```
Examples:

Input : mat1[][] = { {1, 5, 6},
                    {8, 10, 11},
                   {15, 16, 18} }
                         
    mat2[][] = { {2, 4, 7},
                 {9, 10, 12},
                 {13, 16, 20} }
       x = 21 
Output : 4
The pairs are:
(1, 20), (5, 16), (8, 13) and (11, 10).
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;
const int MAX = 52;

int getCount(int a1[][MAX],int a2[][MAX], int n, int x){
    int r1=0, r2 =n-1;
    int c1=0, c2 = n-1;
    int count =0;
    while(r1<n && r2>=0){
        int val = a1[r1][c1] + a2[r2][c2];
        if(val == x){
            count++;
            c1++;
            c2--;
        }
        if(val<x){
            c1++;
        }
        if(val>x){
            c2--;
        }
        if(c1 == n){
            c1 =0;
            r1++;
        }
        if(c2 < 0){
            c2 = n-1;
            r2--;
        }
    }
    return count;
}

int main()
 {
	int test;
	int n,x;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>n>>x;
	    int a1[n][MAX], a2[n][MAX];
	    for(int i=0;i<n;i++){
	        for(int k=0;k<n;k++){
	            cin>>a1[i][k];	        
	        }
	    }
	    for(int i=0;i<n;i++){
	        for(int k=0;k<n;k++){
	            cin>>a2[i][k];	        
	        }
	    }
	    cout<<getCount(a1,a2,n,x)<<endl;
	    
	}
	return 0;
}
```
