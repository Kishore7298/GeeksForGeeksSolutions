##  Missing element of AP 
Find the missing element from  an ordered array A[ ], consisting of N elements representing an Arithmetic Progression (AP) .
 

#### Input:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. 
The first line of each test case contains an integer N, where N is the size of the array A[ ].
The second line of each test case contains N space separated integers of an Arithmetic Progression denoting elements of the array A[ ].
 

Note: The series should have a missing element in between a perfect A.P. with no missing element will not be considered.
 

#### Output:
Print out the missing element. 
 
```
Constraints:
1 <= T <= 100
2 <= N <= 10
-50 <= A[i] <=50
 

Examples :

Input:
3
3 
2 10 14 
4 
-28 -21 -7 0 
5 
9 12 15 21 24

Output : 
6
-14
18
```
#### Solution:
```c++
#include<iostream>
using namespace std;

int missing(int a[],int d, int l, int h){
    if(l < h){
        int m = l+(h-l)/2;
        
        if(a[m+1]-a[m] != d){
            return a[m]+d;
        }
        if(a[m]-a[m-1] != d){
            return a[m-1]+d;
        }
        int am = a[0] + (m*d);
        if(am == a[m]){
            return missing(a,d,m+1,h);
        } else {
            return missing(a,d,l,m-1);
        }
    } else 
        return -1;
}

int missingNumber(int a[],int n){
    int d = (a[n-1]-a[0])/n;
    return missing(a,d,0,n-1);
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
	    cout<<missingNumber(a,n)<<endl;
	}
	return 0;
}
```
