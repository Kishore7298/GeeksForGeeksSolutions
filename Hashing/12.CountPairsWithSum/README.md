##  Count pairs with given sum 
Given an array of integers, and an integer  ‘K’ , find the count of pairs of elements in the array whose sum is equal to 'K'.

#### Input:
First line of the input contains an integer T, denoting the number of test cases. Then T test cases follow. Each test case consists of two lines. First line of each test case contains 2 space separated integers N and K denoting the size of array and the sum respectively. Second line of each test case contains N space separated integers denoting the elements of the array.

#### Output:
Print the count of pairs of elements in the array whose sum is equal to the K.
```
Constraints:
1<=T<=50
1<=N<=50
1<=K<=50
1<=A[i]<=100

Example:
Input
2
4 6
1  5  7 1
4 2
1 1 1 1
Output
2
6
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

int getPairsCount(int arr[], int n, int sum) {    
    unordered_map<int, int> m; 
    for (int i=0; i<n; i++) 
        m[arr[i]]++; 
    int twice_count = 0; 
    for (int i=0; i<n; i++){ 
        twice_count += m[sum-arr[i]]; 
        if (sum-arr[i] == arr[i]) 
            twice_count--; 
    } 
    return twice_count/2; 
} 

int main()
 {
	int test;
	int n,k;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>n>>k;
	    int a[n];
	    for(int i=0;i<n;i++){
	        cin>>a[i];
	    }
	    cout<<getPairsCount(a,n,k)<<endl;
	}
	return 0;
}
```
