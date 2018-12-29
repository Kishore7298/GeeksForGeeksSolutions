##  Count zeros in a sorted matrix 
Given a N x N binary matrix A where each row and column of the matrix is sorted in ascending order , Your task is to complete the function  countZero which returns the count of  number of 0s present in it.

Note : Elements in matrix can be either 1 or 0

#### Input:
The first line of input will be the no of test cases then T test cases will follow . The second line of each test case contains two space separated integers M,N denoting the size of the 2 d matrix . Then in the next lines are the space separated values of the matrix A[ ] [ ] . 

#### Output:
The output will be the number of zeroes present in the square matrix.
```
Constraints:
1<=T<=50
1<=M,N<=50
0<=A[][]<=1
Example:
Input
1
3
0 0 0 0 0 1 0 1 1
Output
6
```
#### Solution:
```c++
int countZeroes(int a[MAX][MAX],int n)
{
    int count =0;
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            if(a[i][j]==0){
                count++;
            }
            else 
                continue;
        }
    }
    return count;
}
```
