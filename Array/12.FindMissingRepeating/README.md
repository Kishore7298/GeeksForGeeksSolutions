## Find Missing And Repeating 

Given an unsorted array of size n. Array elements are in range from 1 to n. One number 'A' from set {1, 2, …n} is missing and one number 'B' occurs twice in array. Find these two numbers.
Note: If you find multiple answers then print the Smallest number found.

#### Input:

The first line of input contains an integer T denoting the number of test cases. The description of T test cases follows.
The first line of each test case contains a single integer N denoting the size of array.
The second line contains N space-separated integers A1, A2, ..., AN denoting the elements of the array.


#### Output:

Print B, the repeating number followed by A which is missing in a single line.

```
Constraints:

1 ≤ T ≤ 40
1 ≤ N ≤ 100
1 ≤ A[i] ≤ N


Example:

Input
2
2
2 2
3 
1 3 3
Output
2 1
3 2
```

### Solution:
##### Approch 1(Inefficient):
```C++
#include<iostream>
#include<algorithm>
using namespace std;

void findMisRep(int a[], int n){
    sort(a,a+n);
    for(int i=0;i<n;i++){
        if(a[i]==a[i+1]){
            printf("%d ",a[i]);
            break;
        }
    }
    for(int j=0;j<n;j++){
        if(a[j] != j+1){
            printf("%d ",j+1);
            break;
        }
    }
    printf("\n");
}

int main()
 {
	int test;
	int n;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    scanf("%d",&n);
	    int a[n];
	    for(int j=0;j<n;j++){
	        scanf("%d",&a[j]);
	    }
	    findMisRep(a,n);
	}
	return 0;
}
```
##### Approch 2(efficient):
```c++
#include<iostream>
#include<stdio.h>
#include<limits.h>
using namespace std;

void findMisRep(int a[], int n){
    
   int min=INT_MAX;
   for(int i=0;i<n;i++){
       if(a[abs(a[i])-1]>0){
           a[abs(a[i])-1] = -a[abs(a[i])-1];
       }else {
           int b = abs(a[i]);
           if(b<min)
               min =b;
       }
   } 
   printf("%d ",min);
   for(int j=0;j<n;j++){
       if(a[j]>0){
           printf("%d",j+1);
           break;
       }
   }
   printf("\n");
}

int main()
 {
	int test;
	int n;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    scanf("%d",&n);
	    int a[n];
	    for(int j=0;j<n;j++){
	        scanf("%d",&a[j]);
	    }
	    findMisRep(a,n);
	}
	return 0;
}
```
