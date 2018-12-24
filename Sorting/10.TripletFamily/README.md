##  Triplet Family 
Given an array A of integers. Find three numbers such that sum of two elements equals the third element and return the triplet in a container result, if no such triplet is found return the container as empty.

#### Input:
First line of input contains number of testcases. For each testcases there will two lines. First line contains size of array and next line contains array elements.

#### Output:
For each test case output the triplets, if any triplet found from the array, if no such triplet is found, output -1.

Your Task: Your task is to complete the function to find triplet and return container containing result.
```
Constraints:
1 <= T <= 100
1 <= N <= 103
0 <= Ai <= 105

Example:
Input:
3
5
1 2 3 4 5
3
3 3 3
6
8 10 16 6 15 25

Output:
1
-1
1

Explanation:
Testcase 1:
Triplet Formed: {2, 1, 3}
Hence 1 
Test Case 2:
Triplet Formed: {}
Hence -1
Test Case 3:
Triplet Formed: {10, 15, 25}
Hence 1
```
#### Solution:
```c++
vector<int> findTriplet(int a[], int n)
{
    vector<int> result;
    sort(a,a+n);
    for(int i=n-1;i>=0;i--){
        int j=0;
        int k = i-1;
        while(j<k){
            if(a[i] ==a[j]+a[k]){
                result.push_back(a[i]);
                result.push_back(a[j]);
                result.push_back(a[k]);
                return result;
            } 
            if(a[i]>a[j]+a[k])
                j++;
            if(a[i]<a[j]+a[k])
                k--;
        }
    }
    return result;
}
```
