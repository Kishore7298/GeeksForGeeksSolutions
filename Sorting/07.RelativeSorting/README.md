## Relative Sorting
Given two array A1[] and A2[], sort A1 in such a way that the relative order among the elements will be same as those  in A2. For the elements not present in A2. Append them at last in sorted order. It is also given that the number of elements in A2[] are smaller than or equal to number of elements in A1[] and A2[] has all distinct elements.
```
Input: A1[] = {2, 1, 2, 5, 7, 1, 9, 3, 6, 8, 8}
       A2[] = {2, 1, 8, 3}
Output: A1[] = {2, 2, 1, 1, 8, 8, 3, 5, 6, 7, 9}
```
Since 2 is present first in A2[], all occurrences of 2s should appear first in A[], then all occurrences 1s as 1 comes after 2 in A[]. Next all occurrences of 8 and then all occurrences of 3.  Finally we print all those elements of A1[] that are not present in A2[]
 

#### Input:

The first line of input contains an integer T denoting the number of test cases. The first line of each test case is M and N.  M is the number of elements in A1 and N is the number of elements in A2.
The second line of each test case contains M elements. The third line of each test case contains N elements.

#### Output:

Print the sorted array according order defined by another array.
```
Constraints:

1 ≤ T ≤ 50
1 ≤ M ≤ 50
1 ≤ N ≤ 10 & N ≤ M
1 ≤ A1[i], A2[i] ≤ 1000

Example:

Input:
1
11 4
2 1 2 5 7 1 9 3 6 8 8
2 1 8 3

Output:
2 2 1 1 8 8 3 5 6 7 9
```
#### Solution:
```c++
#include<iostream>
#include<algorithm>
using namespace std;

int first(int a[],int low,int high,int key){
    while(low<=high){
        int mid = low + (high-low)/2;
        if((mid ==0 || a[mid-1]<key) && a[mid]==key )
            return mid;
         if(a[mid]<key){
             return first(a,mid+1,high,key);
        }
        return first(a,low,mid-1,key);
    }
    return -1;
}

void relativeSort(int a1[], int a2[], int m, int n){
    int temp[m],visited[m];
    for(int i=0;i<m;i++){
        temp[i]=a1[i];
        visited[i]=0;
    }
    sort(temp,temp+m);
    int index=0;
    for(int i=0;i<n;i++){
        int f = first(temp,0,m-1,a2[i]);
        if(f == -1)
            continue;
        for(int j=f;(j<m && temp[j]==a2[i]);j++){
            a1[index++] = temp[j];
            visited[j]=1;
        }
    }
    for(int i=0;i<m;i++){
        if(visited[i]==0){
            a1[index++]=temp[i];
        }
    }
}

void printArray(int arr[], int n) 
{ 
	for (int i=0; i<n; i++) 
		cout << arr[i] << " "; 
	cout << endl; 
} 

int main()
 {
	int test;
	int n,m;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>m>>n;
	    int a1[m],a2[n];
	    for(int j=0;j<m;j++){
	        cin>>a1[j];
	    }
	    for(int j=0;j<n;j++){
	        cin>>a2[j];
	    }
	    relativeSort(a1,a2,m,n);
	    printArray(a1,m);
	}
	return 0;
}
```
