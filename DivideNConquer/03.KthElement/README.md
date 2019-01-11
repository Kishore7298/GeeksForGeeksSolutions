## K-th element of two sorted Arrays
Given two sorted arrays A and B of size M and N respectively and an element k. The task is to find the element that would be at the k’th position of the final sorted array.

#### Input:
First line consists of test cases T. First line of every test case consists of 3 integers N, M and K, denoting M number of elements in A, N number of elements in B and kth position element. Second and Third line of every test case consists of elements of A and B respectively.

#### Output:
Print the element at the Kth position.
```
Constraints:
1 <= T <= 200
1 <= N, M <= 106
1 <= Ai, Bi <= 106
1 <= K <= N+M

Example:
Input:
1
5 4 5
2 3 6 7 9
1 4 8 10

Output:
6

Explanation:
Testcase 1: Element at 5th position after merging both arrays will be 6.
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

int getPosition(int a[],int n, int b[],int m, int k){
    int i=0, j=0;
    int count = 0;
    while(i<n && j<m){
        if(a[i]<=b[j]){
            i++;
            count++;
            if(count == k){
                return a[i-1];
            }
        } else {
            j++;
            count++;
            if(count == k){
                return b[j-1];
            }
        }
    }
    while(i<n){
        if(count == k){
            return a[i-1];
        }
        i++;
        count++;
    }
    while(j<m){
        if(count == k){
            return b[j-1];
        }
        j++;
        count++;
    }
}

int main()
 {
	int test;
	int n,m,k;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>n>>m>>k;
	    int a[n];
	    for(int i=0;i<n;i++){
	        cin>>a[i];
	    }
	    int b[m];
	    for(int i=0;i<m;i++){
	        cin>>b[i];
	    }
	    cout<<getPosition(a,n,b,m,k)<<endl;
	}
	return 0;
}
```
