## Pair with given sum in a sorted array 

You are given an array A of size N. You need to find all pairs in the array that sum to a number K. If no such pair exists then output will be -1. The elements of the array are distinct and are in sorted order.
Note: (a,b) and (b,a) are considered same. Also, an element cannot pair with itself, i.e., (a,a) is invalid.

#### Input:
The first line of input is T denoting the number of testcase. T testcases follow. Each testcase contains three lines of input. The first line is the size of array N. The second line contains N elements separated by spaces. The third line contains the sum K.

#### Output:
For each testcase, print all the pairs such that there sum is equal to K.
```
Constraints:
1 <= T <= 100
0 <= Ai <=107
2 <= N <= 107
0 <= K <= 107

Examples:
Input:
2
7
1 2 3 4 5 6 7
98
7
1 2 3 4 5 6 7
8
Output:
-1
1 7 8
2 6 8
3 5 8
```

##### Explanation:
__Testcase1:__ We cannot find any pair that sums to 98  
__Testcase2:__ We find 3 such pairs that sum to 8 (1,7) (2,6) (3,5)

#### Solution:
```c++
#include<iostream>
using namespace std;

void findPair(int a[], int n, int x){
    int i=0;
    int j= n-1;
    int flag=0;
    while(i<j){
        if(a[i]+a[j]==x){
            printf("%d %d %d\n",a[i],a[j],x);
            flag=1;
            i++;
            j--;
        } else if(a[i]+a[j] < x) {
            i++;
        } else {
            j--;
        }
    }
    if(flag==0){
        printf("-1\n");
    }
    //printf("\n");
}

int main()
 {
	int test;
	int n;
	int x;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    scanf("%d",&n);
	    int a[n];
	    for(int i=0;i<n;i++){
	        scanf("%d",&a[i]);
	    }
	    
	    scanf("%d",&x);
	    findPair(a,n,x);
	}
	return 0;
}
```
