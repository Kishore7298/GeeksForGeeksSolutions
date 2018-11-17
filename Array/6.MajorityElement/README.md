Given an array A of N elements. Find the majority element in the array. A majority element in an array A of size N is an element that appears more than N/2 times.

### Input:  
The first line of the input contains T denoting the number of testcases. The first line of the test case will be the size of array and second line will be the elements of the array.

### Output: 
For each test case the output will be the majority element of the array.
```
Constraints:
1 <= T<= 100
1 <= N <= 103
0 <= Ai <= 103

Example:
Input:
2
5
3 1 3 3 2
3
1 2 3

Output:
3
-1
```
### Solution:
```c++
#include<iostream>
using namespace std;

void findMajority(int a[], int n) 
{ 
    int maxCount=0;
    int index =-1;
    for(int i=0;i<n-1;i++){
        int count=0;
        for(int j=i+1;j<n;j++){
            if(a[i]==a[j]){
                count++;
            }
        }
        if(count>maxCount){
            maxCount=count;
            index=i;
        }
    }
    if(maxCount >= n/2){
        printf("%d\n",a[index]);
    }else {
        printf("-1\n");
    }
} 

int main()
 {
	int test, n;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    scanf("%d",&n);
	    int a[n];
	    for(int j=0;j<n;j++){
	        scanf("%d",&a[j]);
	    }
	    findMajority(a,n);
	}
	return 0;
}
