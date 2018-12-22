## Triplet Sum in Array
Given an array A[] of N numbers and another number x, determine whether or not there exist three elements in A[] whose sum is exactly x.

#### Input:
First line of input contains number of testcases T. For each testcase, first line of input contains n and x. Next line contains array elements.

#### Output:
Print 1 if there exist three elements in A whose sum is exactly x, else 0.
```
Constraints:
1 ≤ T ≤ 100
1 ≤ N ≤ 103
1 ≤ A[i] ≤ 105

Example:
Input:
2
6 13
1 4 45 6 10 8
5 10
1 2 4 3 6

Output:
1
1

Explanation:
Testcase 1: There is one triplet with sum 13 in the array. Triplet elements are 1, 4, 8, whose sum is 13.
```
#### Solution:
```c++
#include<iostream>
#include<algorithm>
using namespace std;

int getSum(int a[],int n,int key){
    sort(a, a+n, greater<int>());
    if(key > a[0]+a[1]+a[2])
        return 0;
    int i,j,k;
    for( i=0;i<n;i++){
        k=n-1;
        j=i+1;
        while(j<k){
            if(a[i]+a[j]+a[k]==key)
                return 1;
            if(a[i]+a[j]+a[k]>key)
                j++;
            if(a[i]+a[j]+a[k]<key)
                k--;
        }
    }
    return 0;
}

int main()
 {
	int test;
	int n,key;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>n>>key;
	    int a[n];
	    for(int j=0;j<n;j++){
	        cin>>a[j];
	    }
	    cout<<getSum(a,n,key)<<endl;
	}
	return 0;
}
```
