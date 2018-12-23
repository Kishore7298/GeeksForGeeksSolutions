##  Sorting Elements of an Array by Frequency 
Given an array of integers, sort the array according to frequency of elements. For example, if the input array is {2, 3, 2, 4, 5, 12, 2, 3, 3, 3, 12}, then modify the array to {3, 3, 3, 3, 2, 2, 2, 12, 12, 4, 5}. 

If frequencies of two elements are same, print them in increasing order.

 

#### Input:

The first line of input contains an integer T denoting the number of test cases. The description of T test cases follows. The first line of each test case contains a single integer N denoting the size of array. The second line contains N space-separated integers A1, A2, ..., AN denoting the elements of the array.


#### Output:

Print each sorted array in a seperate line. For each array its numbers should be seperated by space.

```
Constraints:
1 ≤ T ≤ 70
30 ≤ N ≤ 130
1 ≤ A [ i ] ≤ 60 


Example:

Input:
1
5
5 5 4 6 4

Output:
4 4 5 5 6
```
#### Solution:
```c++
#include<bits/stdc++.h> 
using namespace std; 

struct ele 
{ 
	int count, index, val; 
}; 

bool mycomp(struct ele a, struct ele b) { 
	return (a.val < b.val); 
} 

bool mycomp2(struct ele a, struct ele b) { 
	if (a.count != b.count) return (a.count < b.count); 
	else return a.val > b.val; 
} 

void sortByFrequency(int arr[], int n) 
{ 
	struct ele element[n]; 
	for (int i = 0; i < n; i++) 
	{ 
		element[i].index = i; 
		element[i].count = 0; 
		element[i].val = arr[i]; 
	} 
	stable_sort(element, element+n, mycomp); 
	element[0].count = 1; 
	for (int i = 1; i < n; i++) 
	{ 
		if (element[i].val == element[i-1].val) 
		{ 
			element[i].count += element[i-1].count+1; 
			element[i-1].count = -1; 
			element[i].index = element[i-1].index; 
		} 
		else element[i].count = 1; 
	} 
	stable_sort(element, element+n, mycomp2); 
	for (int i = n-1, index=0; i >= 0; i--) 
		if (element[i].count != -1) 
		for (int j=0; j<element[i].count; j++) 
				arr[index++] = element[i].val; 
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
	    sortByFrequency(a,n);
	    for(int j=0;j<n;j++){
	        cout<<a[j]<<" ";
	    }
	    cout<<endl;
	}
	return 0;
}
```
