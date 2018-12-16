## Floor in a Sorted Array 
Given a sorted array having no duplicates, arr[] and a value, x, find floor of x in given array. Floor of x is the largest element in arr[] such that the element is smaller than or equal to x. If floor exists, then return index of it, else return -1.

Examples:
```
Input : arr[] = {1, 2, 8, 10, 11, 12, 19}, x = 5
Output : 1 
1 is index of 2. 2 is the largest element in arr[]
smaller than 5.

Input : arr[] = {1, 2, 8, 10, 11, 12, 19}, x = 20
Output : 6
19 is the largest element in arr[] smaller than 20.

Input : arr[] = {1, 2, 8, 10, 11, 12, 19}, x = 0
Output : -1
Since floor doesn't exist, output is -1.
```

#### Input:

The first line of input contains an integer T denoting the number of test cases.
The first line of each test case is N and x, N is the size of array.
The second line of each test case contains N array elements.

#### Output:
Print index of floor of x if it exists, else print -1
```
Constraints:

1 ≤ T ≤ 500
1 ≤ N ≤ 1000
0 ≤ X ≤ 1000 
1 ≤ arr[i] ≤ 10000

Example:

Input:
3
7 0
1 2 8 10 11 12 19
7 5
1 2 8 10 11 12 19
7 10
1 2 8 10 11 12 19

Output:
-1
1
3
```
#### Solution:
```c++
#include<iostream>
using namespace std;

int floorArray(int a[], int n, int x){
    int flag=0;
    int max;
    if(a[0]>x){
        return -1;;
    } else {
        max = 0;
    }
    
    for(int i=0;i<n;i++){
        if(a[i]<=x && a[i]>a[max]){
            max = i;
        }
        if(a[i]>x){
            break;
        }
    }
    return max;
}

int main()
 {
	int test;
	int n,x;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>n>>x;
	    int a[n];
	    for(int i=0;i<n;i++){
	        cin>>a[i];
	    }
	    cout<<floorArray(a,n,x)<<endl;
	}
	return 0;
}
```
