## Insertion sort
The task is to complete insert() function which is used to implement Insertion Sort.

#### Input:
First line of the input denotes number of test cases 'T'. First line of the test case is the size of array and second line consists of array elements.


#### Output:
Sorted array in increasing order is displayed to the user.

```
Constraints:
1 <=T<= 50
1 <=N<= 1000
1 <=arr[i]<= 1000


Example:

Input:
2
5
4 1 3 9 7
10
10 9 8 7 6 5 4 3 2 1

Output:
1 3 4 7 9
1 2 3 4 5 6 7 8 9 10
```
#### Solution:
```c++
void insert(int a[], int i)
{
    int key = a[i];
    int j = i-1;
    while(j>=0 && a[j]> key){
        a[j+1] = a[j];
        j--;
    }
    a[j+1]=key; 
}
```
