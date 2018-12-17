##  Missing number 
Vaibhav likes to play with numbers and he has n numbers. One day he was placing the numbers on the playing board just to count that how many numbers he have. He was placing the numbers in increasing order i.e. from 1 to n. But when he was putting the numbers back into his bag, some numbers fell down onto the floor. He picked up all the numbers but one number, he couldn't find. Now he have to go somewhere urgently, so he asks you to find the missing number.

#### Input:
The first of input contains an integer T, then T test cases follow. Each test case contains an integer n i.e. numbers of integers he placed on the board and the second line of each test case contains the array a[] which represents the numbers, he successfully picked up from the floor. 


#### Output:
For each test case in a new line print the missing number.

```
Constraints:
1<=T<=25
1<=n<=10000
1<=a[i]<=10000


Example:
Input:                    
2                                        
4                                        
1 4 3                           
5
2 5 3 1
Output:
2
4
```

#### Explanation:
##### For first test case
Vaibhav placed 4 integers but he picked up only 3 numbers. So missing number will be 2 as it will become 1,2,3,4.

##### For the second case
Vaibhav placed 5 integers on the board, but picked up only 4 integers, so the missing number will be 4 so that it will become 1,2,3,4,5.
#### Solution:
```c++
#include<iostream>
#include<limits.h>
using namespace std;

int findMissing(int a[],int n){
    int Asum=0;
    int max =INT_MIN;
    int min = INT_MAX;
    int size = sizeof(a)/sizeof(a[0]);
    for(int i=0;i<n-1;i++){
        Asum += a[i];
    }
    int Rsum = n*(n+1)/2;
    return Rsum-Asum;
    
}

int main()
 {
	int test;
	int n;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>n;
	    int a[n-1];
	    for(int j=0;j<n-1;j++){
	        cin>>a[j];
	    }
	    cout<<findMissing(a,n)<<endl;
	}
	return 0;
}
```
