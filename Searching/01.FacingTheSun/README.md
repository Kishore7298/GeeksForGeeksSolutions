## Facing the sun 
Monu lives in a society which is having high rise buildings. This is the time of sunrise and monu wants see the buildings receiving the sunlight. Help him in counting the number of buildings recieving the sunlight.
Given an array H representing heights of buildings. You have to count the buildings which will see the sunrise (Assume : Sun rise on the side of array starting point).

### Input:
The first line of input contains an integer T denoting the number of test cases. The first line of each test case is N, N is the number of buildings. The second line of each test case contains N input H[i], height of ith building.

### Output:
Print the total number of buildings which will see the sunset.
```
Constraints:
1 ≤ T ≤ 100
1 ≤ N ≤ 106
1 ≤ Hi ≤ 108

Example:
Input:
2
5
7 4 8 2 9
4
2 3 4 5

Output:
3
4
```
#### Explanation:
<b>Testcase 1:</b> Building with height 7, 8 and 9 will recieve the sunlight during sunrise.

#### Solution:
```c++
#include<iostream>
using namespace std;

void printBuilding(int a[], int n){
    int maxi = a[0];
    int count =1;
    for(int i=1;i<n;i++){
        if(a[i] > maxi){
            count++;
            maxi=a[i];
        }
    }
    cout<<count<<endl;
}

int main()
 {
	int test;
	int n;
	cin>>test;
	//cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>n;
	    int a[n];
	    for(int j=0;j<n;j++)
	        cin>>a[j];
	    printBuilding(a,n);
	}
	return 0;
}
```
