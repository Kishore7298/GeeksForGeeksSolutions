You are given an array A, of N elements. You need to find minimum distance between given two integers x and y.

### Input Format:
The first line of input contains an integer T, denoting the number of test cases. Then T test cases follow. Each test case consists of three lines. The first line of each test case contains an integer N denoting size array. Then in the next line are N space separated values of the array A. The last line of each test case contains two integers  x and y.

### Output Format:
For each test case, print the required answer .

#### Your Task:
Your task is to complete the function minDist which returns  an integer denoting the minimum distance between two integers x and y in the array. If no such distance is possible then return -1.
```
Constraints:
1 <= T <= 100
1 <= N <= 100
1 <= A, x, y <= 100

Example:
Input:
2
2
1 2
1 2
7
86 39 90 67 84 66 62 
42 12

Output:
1
-1
```

### Solution:

```C++
{
#include <stdio.h>
#include<iostream>
#include <stdlib.h> // for abs()
#include <limits.h> // for INT_MAX
 using namespace std;
int minDist(int arr[], int n, int x, int y);
int main() 
{
	int t;
	cin>>t;
	while(t--){
		int n;
		cin>>n;
		int a[n];
		for(int i=0;i<n;i++)
			cin>>a[i];
		int x,y;
		cin>>x>>y;
		cout<<minDist(a,n,x,y)<<endl;
	}
    return 0;
}
}

/*Complete the function below*/
int minDist(int a[], int n, int x, int y)
{  
    int minDis = INT_MAX;
    int prev;
    int i=0;
    for(i=0;i<n;i++){
        if(a[i]==x || a[i]==y){
            prev = i;
            break;
        }
    }
    for(;i<n;i++){
        if(a[i]==x || a[i]==y){
            if(a[prev] != a[i] && (i-prev)<minDis){
                minDis= i-prev;
                prev =i;
            }
            else
                prev =i;
        }
    }
    if(minDis == INT_MAX){
        return -1;
    }
    return minDis;
}
