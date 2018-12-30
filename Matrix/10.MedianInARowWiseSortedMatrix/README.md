##  Median In a Row-Wise sorted Matrix 
We are given a row wise sorted matrix of size r*c, we need to find the median of the matrix given. It is assumed that r*c is always odd.

#### Input:
The first line of input contains an integer T denoting the number of test cases. Each test case contains two integers r and c, where r is the number of rows and c is the number of columns in the array a[]. Next r line contains space separated c elements each in the array a[].​

#### Output:
Print an integer which is the median of the matrix.
```
Constraints:
1<= T <=100
1<= r,c <=150
1<= a[i][j] <=1000

Example:
Input:
1
3 3
1 3 5
2 6 9
3 6 9

Output:
5
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;
const int MAX =152;

int getMedian(int a[][MAX], int r, int c){
    int min = INT_MAX;
    int max = INT_MIN;
    for(int i=0;i<r;i++){
        if(a[i][0] <min){
            min = a[i][0];
        }
        if(a[i][c-1] >max){
            max = a[i][c-1];
        }
    }
    int desired = (r*c+1)/2;
    while(min < max){
        int mid = min +(max-min)/2;
        int count =0;
        for(int i=0;i<r;i++){
            count += upper_bound(a[i], a[i]+c, mid)-a[i];
        }
        if(count < desired){
            min = mid+1;
        } else {
            max = mid;
        }
    }
    return min;
    
}

int main()
 {
	int test;
	int r,c;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>r>>c;
	    int a[r][MAX];
	    for(int i=0;i<r;i++){
	        for(int k=0;k<c;k++){
	            cin>>a[i][k];
	        }
	    }
	    cout<<getMedian(a,r,c)<<endl;
	}
	return 0;
}
```
