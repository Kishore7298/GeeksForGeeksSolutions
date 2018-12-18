## Find Transition Point
You are given a sorted array containing only numbers 0 and 1. Find the transition point efficiently. Transition point is a point where "0" ends and "1" begins.

#### Input:

You have to complete the method which takes 2 argument: the array arr[] and size of array N. You should not read any input from stdin/console. There are multiple test cases. For each test cases, this method will be called individually.

#### Output:

Your function should return transition point.
```
Constraints:

1 ≤ T ≤ 100
1 ≤ N ≤ 500000
0 ≤ C[i] ≤ 1

Example:

Input
1
5
0 0 0 1 1

Output
3
```
#### Solution:
```c++
int transitionPoint(int a[],int n)
{
    int start =0, end=n-1,ans;
    while(start<=end){
        int mid = start + (end-start)/2;
        if(a[mid] == 1){
            end =mid-1;
            ans = mid;
        }else{
            start = mid+1;
        }
        
    }
    return ans;
}
```
