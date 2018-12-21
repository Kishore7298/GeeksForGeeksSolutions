## Merge Sort 
The task is to complete merge() function which is used to implement Merge Sort.

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
void merge(int arr[], int l, int m, int r)
{
     int n1 = m-l+1;
     int n2 = r-m;
     int i,j,k;
     int L[n1], R[n2];
     for(int i=0;i<n1;i++){
         L[i] = arr[l+i];
     }
     for(int j=0;j<n1;j++){
         R[j] = arr[m+1+j];
     }
     i=0;j=0;k=l;
     while(i<n1&&j<n2){
         if(L[i]<=R[j]){
             arr[k]=L[i++];
         } else {
             arr[k]=R[j++];
         }
         k++;
     }
     while(i<n1){
         arr[k++]=L[i++];
     }
     while(j<n2){
         arr[k++]=R[j++];
     }
}
```
