##  Print Pattern 
Print a sequence of numbers starting with N, without using loop, in which  A[i+1] = A[i] - 5,  if  A[i]>0, else A[i+1]=A[i] + 5  repeat it until A[i]=N.

#### Input:
The first line contains an integer T, number of test cases. Then following T lines contains an integer N.

#### Output:
For each test case, print the pattern in newline with space separated integers.
```
Constraints:
0< N < 10000

Example:
Input:
2
16
10
Output:
16 11 6 1 -4 1 6 11 16
10 5 0 5 10

Explanation:
We basically first reduce 5 one by one until we reach a negative or 0. After we reach 0 or negative, 
we one by one add 5 until we reach N.
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

void printNumber(int num){
    if(num>0){
        cout<<num<<" ";
        printNumber(num-5);
    }
    cout<<num<<" ";
}

int main()
 {
	int test;
	int n;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>n;
	    printNumber(n);
	    cout<<endl;
	}
	return 0;
}
```
