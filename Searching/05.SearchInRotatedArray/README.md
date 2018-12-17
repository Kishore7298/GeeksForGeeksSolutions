## Search in a Rotated Array 
Given a sorted and rotated array A of N distinct elements which is rotated at some point, and given an element K. The task is to find the index of the given element K in the array A.

#### Input:
The first line of the input contains an integer T, denoting the total number of test cases. Then T test cases follow. Each test case consists of three lines. First line of each test case contains an integer N denoting the size of the given array. Second line of each test case contains N space separated integers denoting the elements of the array A. Third line of each test case contains an integer K denoting the element to be searched in the array.

#### Output:
Corresponding to each test case, output the index of the element found in the array.  If element is not present, then output -1.
```
Constraints:
1 ≤ T ≤ 100
1 ≤ N ≤ 107
0 ≤ Ai ≤ 108
1 ≤ K ≤ 108

Example:
Input:
3
9
5 6 7 8 9 10 1 2 3
10
3
3 1 2
1
4
3 5 1 2
6

Output:
5
1
-1
```
##### Explanation:
Testcase 1: 10 is found at index 5.
#### Solution:
##### Approach 1:
```c++
#include<iostream>
using namespace std;

int findIndex(int a[], int n, int x){
    //int index, flag=0;
    //for(int i=1;i<n;i++){
    //    if(a[i-1]>a[i]){
    //        index =i;
    //        flag=1;
    //        break;
    //    }
    //}
    //int l = index;
    //int r = n-index;
    //if(flag ==0){
        int i;
        for(i=0;i<n;i++){
            if(a[i]==x)
                return i;
        }
        if(i = n-1){
            return -1;
        }
   // }
   // int j;
   // for(j =0;j<n;j++){
   //     if(a[j]==x){
   //         if(j>=index){
   //             return j-l;
   //         } else {
   //             return j+r;
   //         }
   //     }
   // }
   // if(j == n-1){
   //     return -1;
   // }
}

int main()
 {
	int test;
	int n,x;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>n;
	    int a[n];
	    for(int j=0;j<n;j++){
	        cin>>a[j];
	    }
	    cin>>x;
	    cout<<findIndex(a,n,x)<<endl;
	}
	return 0;
}
```
##### Approach 2:
```c++
/* C++ Program to search an element 
in a sorted and pivoted array*/
#include <bits/stdc++.h> 
using namespace std; 

/* Standard Binary Search function*/
int binarySearch(int arr[], int low, 
				int high, int key) 
{ 
if (high < low) 
	return -1; 
	
int mid = (low + high)/2; /*low + (high - low)/2;*/
if (key == arr[mid]) 
	return mid; 
	
if (key > arr[mid]) 
	return binarySearch(arr, (mid + 1), high, key); 
	
// else 
	return binarySearch(arr, low, (mid -1), key); 
} 

/* Function to get pivot. For array 3, 4, 5, 6, 1, 2 
it returns 3 (index of 6) */
int findPivot(int arr[], int low, int high) 
{ 
// base cases 
if (high < low) return -1; 
if (high == low) return low; 

int mid = (low + high)/2; /*low + (high - low)/2;*/
if (mid < high && arr[mid] > arr[mid + 1]) 
	return mid; 
	
if (mid > low && arr[mid] < arr[mid - 1]) 
	return (mid-1); 
	
if (arr[low] >= arr[mid]) 
	return findPivot(arr, low, mid-1); 
	
return findPivot(arr, mid + 1, high); 
} 

/* Searches an element key in a pivoted 
sorted array arr[] of size n */
int pivotedBinarySearch(int arr[], int n, int key) 
{ 
int pivot = findPivot(arr, 0, n-1); 

// If we didn't find a pivot, 
// then array is not rotated at all 
if (pivot == -1) 
	return binarySearch(arr, 0, n-1, key); 

// If we found a pivot, then first compare with pivot 
// and then search in two subarrays around pivot 
if (arr[pivot] == key) 
	return pivot; 
	
if (arr[0] <= key) 
	return binarySearch(arr, 0, pivot-1, key); 
	
	return binarySearch(arr, pivot+1, n-1, key); 
} 

/* Driver program to check above functions */
int main() 
{ 
// Let us search 3 in below array 
int arr1[] = {5, 6, 7, 8, 9, 10, 1, 2, 3}; 
int n = sizeof(arr1)/sizeof(arr1[0]); 
int key = 3; 
	
// Function calling 
cout << "Index of the element is : " << 
		pivotedBinarySearch(arr1, n, key); 
			
return 0; 
} 

```
