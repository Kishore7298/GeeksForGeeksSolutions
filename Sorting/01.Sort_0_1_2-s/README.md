##  Sort an array of 0s, 1s and 2s 
Given an array A of size N containing 0s, 1s, and 2s; you need to sort the array in ascending order.

#### Input:
The first line contains an integer 'T' denoting the total number of test cases. Then T testcases follow. Each testcases contains two lines of input. The first line denotes the size of the array N. The second lines contains the elements of the array A separated by spaces.

#### Output: 
For each testcase, print the sorted array.
```
Constraints:
1 <= T <= 500
1 <= N <= 106
0 <= Ai <= 2

Example:
Input :
2
5
0 2 1 2 0
3
0 1 0

Output:
0 0 1 2 2
0 0 1
```
##### Explanation:
Testcase 1: After segragating the 0s, 1s and 2s, we have 0 0 1 2 2 which shown in the output.

#### Solution:
```c++
#include<iostream>
using namespace std;

void printSorted(int a[],int n){
    int count[3] = {0};
    for(int i=0;i<n;i++){
        count[a[i]]++;
    }
    for(int i=0;i<3;i++){
        for(int j=0;j<count[i];j++){
            cout<<i<<" ";
        }
   }
    cout<<endl;
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
	    printSorted(a,n);
	}
	return 0;
}
```
