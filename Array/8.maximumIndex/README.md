Given an array A of integers, find the maximum of j - i subjected to the constraint of A[i] <= A[j].
```
Example :

A : [3 5 4 2]

Output : 2 
for the pair (3, 4)
```
 

#### Input:

The first line contains an integer T, depicting total number of test cases. 
Then following T lines contains an integer N depicting the size of array and next line followed by the value of array.


#### Output:

Print the maximum difference of the indexes i and j in a separtate line.

```
Constraints:

1 ≤ T ≤ 100
1 ≤ N ≤ 1000
0 ≤ A[i] ≤ 100


Example:

Input
1
2
1 10
Output
1
```
### Solution:
##### Approch1(Inefficient):
```c++
#include<iostream>
using namespace std;
void getMaxIndex(int a[], int n){
    int maxIndex=-1;
    for(int i=0;i<n-1;i++){
        for(int j=n-1;j>i;j--){
            if(a[i]<=a[j] && maxIndex < (j-i)){
                maxIndex=j-i;
            }
        }
    }
    if(maxIndex == -1){
        printf("0\n");
    }
    else
        printf("%d\n",maxIndex);
    
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
	    getMaxIndex(a,n);
	}
	return 0;
}
```
##### Approch2:
```c++
#include<iostream>
using namespace std;

int max(int x, int y) 
{ 
    return x > y? x : y; 
} 
  
int min(int x, int y) 
{ 
    return x < y? x : y; 
} 

void getMaxIndex(int arr[], int n){
    int maxDiff; 
    int i, j; 
  
    int *LMin = (int *)malloc(sizeof(int)*n); 
    int *RMax = (int *)malloc(sizeof(int)*n); 
  
   /* Construct LMin[] such that LMin[i] stores the minimum value 
       from (arr[0], arr[1], ... arr[i]) */
    LMin[0] = arr[0]; 
    for (i = 1; i < n; ++i) 
        LMin[i] = min(arr[i], LMin[i-1]); 
  
    /* Construct RMax[] such that RMax[j] stores the maximum value 
       from (arr[j], arr[j+1], ..arr[n-1]) */
    RMax[n-1] = arr[n-1]; 
    for (j = n-2; j >= 0; --j) 
        RMax[j] = max(arr[j], RMax[j+1]); 
  
    /* Traverse both arrays from left to right to find optimum j - i 
        This process is similar to merge() of MergeSort */
    i = 0, j = 0, maxDiff = -1; 
    while (j < n && i < n) 
    { 
        if (LMin[i] <= RMax[j]) 
        { 
            maxDiff = max(maxDiff, j-i); 
            j = j + 1; 
        } 
        else
            i = i+1; 
    } 
    if(maxDiff == -1){
        printf("0\n");
    }
    else
        printf("%d\n",maxDiff);
    
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
	    getMaxIndex(a,n);
	}
	return 0;
}
