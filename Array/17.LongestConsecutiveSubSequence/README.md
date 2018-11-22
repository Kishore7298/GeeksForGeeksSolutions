## Longest Consecutive Subsequence

Given an array A of integers. The task is to complete the function which returns an integer denoting the length of the longest sub-sequence such that elements in the sub-sequence are consecutive integers, the consecutive numbers can be in any order.

#### Input:
The first line of input contains an integer T denoting the no of test cases. Then T test cases follow. Each test case contains an integer N. Then in the next line are N space separated values of the array A.

#### Output:
For each test case in a new line output will be the length of the longest consecutive increasing sub-sequence present in the array A[ ].
```
Constraints:
1 <= T <= 100
1 <= N <= 106
1 <= Ai <= 108

Example(To be used only for expected output):
Input:
2
7
1 9 3 10 4 20 2
11
36 41 56 35 44 33 34 92 43 32 42
Output:
4
5
```
##### Explanation:
<h5>Testcase 1:</h5> Logest consecutive subsequence is 1, 2, 3, 4 of length 4.
  
#### Solution:
```c++
int findLongestConseqSubseq(int a[], int n)
{
    sort(a,a+n);
    int max= 0;
    int count =0;
    for(int i=0;i<n;i++){
        if(a[i]+1 == a[i+1])
            count++;
        else if(a[i] == a[i+1]){
            continue;
        }
        else {
            if(max<count)
                max=count;
            count =0;
        }
    }
    return max+1;
}
```
