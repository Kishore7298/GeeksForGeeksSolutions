Given an unsorted array of positive integers. Find the number of triangles that can be formed with three different array elements as lengths of three sides of triangles. 

### Input: 
The first line of the input contains T denoting the number of testcases. First line of test case is the length of array N and second line of test case are its elements.

### Output:
Number of possible triangles are displayed to the user.

```
Constraints:
1 <= T <= 200
3 <= N <= 107
1 <= arr[i] <= 103

Example:
Input:
2
3
3 5 4
5
6 4 9 7 8

Output:
1
10
```
## Solution:
```C++
#include<iostream>
#include <bits/stdc++.h> 
using namespace std;

void possibleTriangle(int a[], int length){
    int count=0;
    sort(a, a+length);
    for(int i=0;i<length-2;i++){
        int k=i+2;
        for(int j=i+1;j<length;j++){
            while(k<length && (a[i]+a[j] > a[k]))
                k++;
            
            if(k>j){
                count += k-j-1;
            }
        }
    }
    printf("%d\n",count);
}

int main()
 {
	int t,length;
	scanf("%d",&t);
	for(int i=0;i<t;i++){
	    scanf("%d",&length);
	    int a[length];
	    for(int j=0;j<length;j++){
	        scanf("%d",&a[j]);
	    }
	    possibleTriangle(a,length);
	}
	return 0;
}
