##  Print Matrix in snake Pattern 
Given an n x n matrix .In the given matrix, you have to print the elements of the matrix in the snake pattern.
![alt text](https://contribute.geeksforgeeks.org/wp-content/uploads/snake-pattern.jpg)
#### Input:
First line consists of T test cases. First line of every test case consists of N, denoting number of elements(N x N) in Matrix. Second line of every test case consists of N x N spaced integers denoting elements of Matrix elements.

#### Output:
Single line output, print the matrix in snake pattern.
```
Constraints:
1<=T<=100
1<=N<=50

Example:
Input:
1
3
45 48 54 21 89 87 70 78 15 
Output:
45 48 54 87 89 21 70 78 15 
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;
const int MAX = 100;

void printSnakePattern(int a[][MAX], int n){
    for(int i=0;i<n;i++){
        if(i%2 ==0){
            for(int j=0;j<n;j++){
                cout<<a[i][j]<<" ";
            }
        } else {
            for(int j = n-1; j>=0;j--){
                cout<<a[i][j]<<" ";
            }
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
	    printSnakePattern(a,n);
	    cout<<endl;
	}
	return 0;
}
```
