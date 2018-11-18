Given two arrays A and B. The task is to complete the function max_path_sum that takes 4 argument, the first two arguments represent the 2 arrays A[] and B[] and the last two arguments l1, l2 denote the size of array A and B respectively. The function returns the sum of the maximum sum path to reach from beginning of any array to end of any of the two arrays .

##### Note: You can switch from one array to another array only at common elements.

#### Input:
The first line of input contains an integer T denoting the no of test cases . Then T cases follow.
Each test case contains 3 lines. The first line contains two space separated integers l1 and l2 denoting the length of the two sorted array A and B. In the second line is the space separated values of array A and in the third line are space separated values of array B.

#### Output:
For each test case the output is the max sum obtained in such fashion .
```
Constraints:
1 <= T <= 100
1 <= N, M <= 103
1 <= A[], B[] <= 104

Example:
2
5 4
2 3 7 10 12
1 5 7 8 
3 3
1 2 4
1 2 7

Output
35 
10
```
##### Explanation:
###### Testcase 1: 
For first test case the path will be 1+5+7+10+12 = 35.
###### Testcase 2: 
For second test case the path will be 1+2 +7=10.

##### Note:
The Input/Ouput format and Example given are used for system's internal purpose, and should be used by a user for Expected Output only. As it is a function problem, hence a user should not read any input from stdin/console. The task is to complete the function specified, and not to write the full code.

#### Solution:
```C++
int max(int a, int b){
    return a>b?a:b;
}
 int max_path_sum(int A[], int B[], int l1, int l2)
{
    int i=0,j=0;
    int res=0;
    int sum1=0,sum2=0;
    
    while(i<l1 && j<l2){
        if(A[i]<B[j]){
            sum1 += A[i++];
        } else if(A[i]>B[j]){
            sum2 += B[j++];
        } else {
            res+= max(sum1,sum2);
            sum1=0;
            sum2=0;
            while((i<l1 && j<l2)&&(A[i]==B[j])){
                res += A[i++];
                j++;
            }
        }
    }
    while(i<l1){
        sum1+=A[i++];
    }
    while(j<l2){
        sum2+=B[j++];
    }
    res += max(sum1, sum2);
    return res;
}
