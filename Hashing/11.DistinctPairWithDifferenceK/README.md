##  Count distinct pairs with difference k 
Given an integer array and a non-negative integer k, count all distinct pairs with difference equal to k, i.e., A[ i ] - A[ j ] = k.
#### Input:

The first line of input consists number of the test cases. The description of T test cases is as follows:

The first line of each test case contains the size of the array, the second line has the elements of the array and the third line consists of the difference k.

#### Output:

In each separate line print the number of times difference k exists between the elements of the array.

```
Constraints:

1 ≤ T ≤ 100
1 ≤ N≤ 100
0≤K≤100
0 ≤ A[i] ≤ 10000


Example:

Input:

3
5 
1 5 4 1 2
0
3
1 1 1
0
3 
1 5 3
2

Output:

1
1
2
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

int getCount(int a[],int n, int x){
    int count =0;
    unordered_set<int> hash;
    for(int i=0;i<n;i++){
        hash.insert(a[i]);
    }
    for(int i=0;i<n;i++){
        int m = a[i]+x;
        
        if(hash.find(m) != hash.end()){
            count++;
        }
            
    }
    return count;
}

int main()
 {
	int test;
	int n;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>n;
	    int a[n],x;
	    for(int i=0;i<n;i++){
	        cin>>a[i];
	    }
	    cin>>x;
	    if(x!=0)
	        cout<<getCount(a,n,x)<<endl;
	    else
	        cout<<"1"<<endl;
	}
	return 0;
}
```
