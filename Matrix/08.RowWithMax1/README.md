##  Row with max 1s 
Given a boolean 2D array where each row is sorted. Find the row with the maximum number of 1s.

#### Input:
The first line of input contains an integer T denoting the number of test cases.
The first line of each test case contains n and m, where n is the number of rows and m is the number of columns. The second line of each test case contains the array elements.

#### Output:
Print the row with the maximum number of 1s.
```
Constraints:
1 ≤ T ≤ 50
1 ≤ n,m ≤ 103

Example:
Input:
1
4 4
0 1 1 1 0 0 1 1 1 1 1 1 0 0 0 0

Output:
2

Explanation :
Testcase 1 : Row 2 is having maximum number of 1s (0-based indexing).
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;
int main()
 {
	int test;
	int n,m;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>n>>m;
	    int a[n][m];
	    int count =0;
	    int index;
	    int maxCount =0;
	    for(int i=0;i<n;i++){
	        count =0;
	        for(int k=0;k<m;k++){
	            cin>>a[i][k];
	            if(a[i][k]==1)
	                count++;
	            if(count>maxCount){
	                maxCount= count;
	                index =i;
	            }
	        }
	    }
	    cout<<index<<endl;
	}
	return 0;
}
```
