##  Largest Fibonacci Subsequence 
Given an array with positive number the task to find the largest subsequence from array that contain elements which are Fibonacci numbers.

#### Input:
The first line of input contains an integer T denoting the no of test cases. Then T test cases follow. Each test case contains an integer N denoting the size of the array. Then in the next line are N space separated values of the array.

#### Output:
For each test case in a new line print the space separated elements of the  longest fibonacci subsequence.
```
Constraints:
1<=T<=100
1<=N<=100
1<=A[]<=1000

Example:
Input:
2
7
1 4 3 9 10 13 7
9
0 2 8 5 2 1 4 13 23

Output:
1 3 13
0 2 8 5 2 1 13 
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

void findFibSubset(int arr[], int n){ 
    int max = *std::max_element(arr, arr+n); 
    int a = 0, b = 1; 
    unordered_set<int> hash; 
    hash.insert(a); 
    hash.insert(b); 
    while (b < max){ 
        int c = a + b; 
        a = b; 
        b = c; 
        hash.insert(b); 
    } 
    for (int i=0; i<n; i++) 
        if (hash.find(arr[i]) != hash.end()) 
            printf("%d ", arr[i]); 
} 

int main()
{
	int test;
	int n;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>n;
	    int a[n];
	    for(int i=0;i<n;i++){
	        cin>>a[i];
	    }
	    findFibSubset(a,n);
	    cout<<endl;
	}
	return 0;
}
```
