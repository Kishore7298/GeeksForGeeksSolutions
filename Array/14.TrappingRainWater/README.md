## Trapping Rain Water 

Given an array A of N non-negative integers representing height of blocks at index i as Ai where the width of each block is 1. Compute how much water can be trapped in between blocks after raining.
Structure is like below:
```
| |
|_|
```
We can trap 2 units of water in the middle gap.

#### Input:
The first line of input contains an integer T denoting the number of test cases. The description of T test cases follows. Each test case contains an integer N followed by N numbers to be stored in array.

#### Output:
Output the total unit of water trapped in between the blocks.
```
Constraints:
1 <= T <= 100
3 <= N <= 107
0 <= Ai <= 107

Example:
Input:
2
4
7 4 0 9
3
6 9 9

Output:
10
0
```
Explanation:
Testcase 1: Water trapped by block of height 4 is 3 units, block of height 0 is 7 units. So, total unit of water trapped is 10 units.

#### Solution:
```c++
#include<iostream>
#include<bits/stdc++.h>
using namespace std;

void waterLevel(int a[], int n){
    int water=0;
    int left[n];
    int right[n];
    
    left[0]=a[0];
    for(int i=1;i<n;i++){
        left[i] = max(left[i-1],a[i]);
    }
    right[n-1]=a[n-1];
    for(int i=n-2;i>=0;i--){
        right[i] = max(right[i+1],a[i]);
    }
    for(int i=0;i<n;i++){
        water += min(left[i],right[i])-a[i];
    }
    printf("%d\n",water);
}

int main()
 {
	int test;
	int n;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    scanf("%d",&n);
	    int a[n];
	    for(int i=0;i<n;i++){
	        scanf("%d",&a[i]);
	    }
	    waterLevel(a,n);
	}
	return 0;
}
```
