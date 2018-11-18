Given an array A of integers. Sort the array into a wave-like array and return it. In other words, arrange the elements into a sequence such that a1 >= a2 <= a3 >= a4 <= a5.....

#### Input:
The first line contains an integer T, depicting total number of test cases. Then following T lines contains an integer N depicting the size of square matrix and next line followed by the value of array.

#### Output:
Print the array into wave-like array.
```
Constraints:
1 ≤ T ≤ 130
1 ≤ N ≤ 104
0 ≤ A[i] ≤105

Example:
Input:
1
5
5 7 3 2 8
Output:
3 2 7 5 8
```
##### Explanation:
Testcase 1: Array elements after sorting it in wave form are 3, 2, 7, 5, 8.

### Solution:

#### Approach1:
```c++
#include<iostream>
#include<bits/stdc++.h>
using namespace std;
void waveSort(int a[], int n){
    sort(a,a+n);
    for(int i=0;i<n-1;i+2){
        swap(a[i],a[i+1]);
    }
    for(int i=0;i<n;i++){
        printf("%d",a[i]);
    }
    
}
int main()
 {
	int test, n;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    scanf("%d",&n);
	    int a[n];
	    for(int j=0;j<n;j++){
	        scanf("%d",&a[j]);
	    }
	    waveSort(a,n);
	}
	return 0;
}
```
#### Approach2(efficient):
##### Note: This works with O(n) but applies only if the wave sort needen't be in sorted order.
```c++
#include<iostream>
#include<bits/stdc++.h>
using namespace std;
void waveSort(int a[], int n){
    for(int i=0;i<n; i+=2){
        if(i>0 && a[i-1]>a[i])
            swap(a[i-1],a[i]);
        if(i<n-1 && a[i+1]>a[i])
            swap(a[i+1],a[i]);
    }
    for(int j=0;j<n;j++){
        printf("%d ",a[j]);
    }
    printf("\n");
}
int main()
 {
	int test, n;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    scanf("%d",&n);
	    int a[n];
	    for(int j=0;j<n;j++){
	        scanf("%d",&a[j]);
	    }
	    waveSort(a,n);
	}
	return 0;
}
