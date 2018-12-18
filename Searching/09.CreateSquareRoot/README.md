## Square root
Given an integer x , Your task is to find the  square root of it. If x is not a perfect square, then return floor(√x).

#### Input Format:
First line of input contains number of testcases T. For each testcase, the only line contains the number x.

#### Output Format:
For each testcase, print square root of given integer.

##### User Task:
The task is to complete the function floorSqrt() which should return the square root of given number x.
```
Constraints:
1 ≤ T ≤ 1000
1 ≤ N ≤ 1000000

Example:
Input:
2
5
4

Output:
2
2
```
##### Explanation:
<h6>Testcase 1:</h6> Since, 5 is not perfect square, so floor of square_root of 5 is 2.
<h6>Testcase 2:</h6> Since, 4 is a perfect square, so its square root is 2.

#### Solution:
```c++
long long int floorSqrt(long long int x) 
{
    if(x==1 || x ==0){
        return x;
    }
    long long start=1, end =x;
    long long ans;
    
    while(start <= end){
        long long middle = (start +end)/2;
        if(middle*middle == x){
            return middle;
        }
        if(middle*middle <x){
            start = middle+1;
            ans = middle;
        } else {
            end = middle-1;
        }
    }
    return ans;
}
```
