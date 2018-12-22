## Quick Sort
The task is to complete partition() function which is used to implement Quick Sort.

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
void quickSort(int arr[], int low, int high) {
    if (low < high)     {
        // pi is partitioning index, arr[p] is now  at right place
        int pi = partition(arr, low, high);
        // Separately sort elements before / partition and after partition
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}
int partition (int a[], int low, int high)
{
   int pivot = a[high];
   int i = low-1;
   for(int j=low;j<high;j++){
       if(a[j]<=pivot){
           i++;
           swap(a[i],a[j]);
       }
   }
   swap(a[i+1],a[high]);
   return i+1;
}
```
