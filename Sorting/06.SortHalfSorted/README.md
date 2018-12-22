## Sort the Half Sorted 
Given an integer array of which both first half and second half are sorted. The task is to merge two sorted halves of the array into a single sorted array.

#### Input:
The first line of input contains an integer T denoting the number of test cases. Each test case contains an integer n which denotes the number of elements in the array a[]. Next line contains space separated n elements in the array a[].

#### Output:
Print the sorted array with space separated values.
```
Constraints:
1<=T<=100
1<=n<=1000
-1000<=a[i]<=1000

Example:
Input:
2
6
2 3 8 -1 7 10
5
-4 6 9 -1 3

Output:
-1 2 3 7 8 10 
-4 -1 3 6 9 
```
#### Solution:
```c++
#include<iostream>
using namespace std;

int getIndex(int a[],int n){
    for(int i=1;i<n;i++){
        if(a[i-1]>a[i])
            return i;
    }
}

void mergeSort(int a[], int p, int n){
    int n1 = p;
    int n2 = n-p;
    int L[n1],R[n2];
    int i=0,j=0,k=0;
    for(i=0;i<n1;i++){
        L[i]=a[k++];
    }
    
    for(j=0;j<n2;j++){
        R[j]=a[k++];
    }
    i=0;j=0;k=0;
    while(i<n1 && j<n2){
        if(L[i]>R[j]){
            a[k++]=R[j++];
        } else {
            a[k++] = L[i++];
        }
    }
    while(i<n1){
        a[k++]=L[i++];
    }
    while(j<n2){
        a[k++]=R[j++];
    }
    
}

int sort(int a[],int n){
    if(n == 1 || n ==0){
        return 1;
    }
    int p = getIndex(a,n);
	mergeSort(a,p,n);
	return 1;
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
	    int s = sort(a,n);
	    for(int j=0;j<n;j++){
	        cout<<a[j]<<" ";
	    }
	    cout<<endl;
	}
	return 0;
}
```
