##  Squares in a Matrix 
Given a MxN matrix, count the number of squares in the matrix.
![alt text](https://www.geeksforgeeks.org//wp-content/uploads/squaresinREct.png)
#### Input:
The first line of input contains an integer T denoting the no of test cases. Then T test cases follow. Each test case contains two space seperated integers M and N, denoting the size of the Matrix.
#### Output:
For each test output a single integer denoting the total number of squares.
```
Constraints:
1<=T<=102
1<=M,N<=10^4

Example:

Input:
2
2 2
4 3

Output:
5
20
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

long long getSquares(long long m,long long n){
    if(m>n)
        swap(m,n);
    return m*(m+1)*(2*m+1)/6+(n-m)*m*(m+1)/2;
}

int main()
 {
	int test;
	long long n,m;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>m>>n;
	    cout<<getSquares(m,n)<<endl;
	}
	return 0;
}
```
