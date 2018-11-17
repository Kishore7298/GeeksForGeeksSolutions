Given a sorted array A of size N. The function remove_duplicate takes two arguments . The first argument is the sorted array A[ ] and the second argument is 'N' the size of the array and returns the size of the new converted array A[ ] with no duplicate element.

### Input Format:
The first line of input contains T denoting the no of test cases . Then T test cases follow . The first line of each test case contains an Integer N and the next line contains N space separated values of the array A[ ] .

### Output Format:
For each test case output will be the transformed array with no duplicates.

Your Task:
Your task to complete the function remove_duplicate which removes the duplicate  elements from the array .
```
Constraints:
1 <= T <= 100
1 <= N <= 104
1 <= A[ ] <= 106

Example:
Input  (To be used only for expected output) :
2
5
2 2 2 2 2 
3
1 2 2
Output
2
1 2
```

Solution:

Approch1:
```C++
int remove_duplicate(int A[],int N)
{
//Your code here
    int temp[N];
    int j=0;
    
    for(int i=0;i<N-1;i++)
        if(A[i] != A[i+1]){
            temp[j++] = A[i];
        }
    temp[j++] = A[N-1];
    for(int k=0;k<j;k++){
        A[k]=temp[k];
    }
    return j;
}
```
Approach2:
```C++
int remove_duplicate(int A[],int N)
{    
   int fin =0;
		for(int i=1;i<N;++i)
			if(A[i]!=A[fin])
			A[++fin]=A[i];
 return fin+1;
}
