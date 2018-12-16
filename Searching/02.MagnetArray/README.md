##  Magnet Array Problem 
Given n Magnets which are placed linearly, with each magnet to be considered as of point object. Each magnet suffers force from its left sided magnets such that they repel it to the right and vice versa. All forces are repulsive. The force being equal to the distance (1/d , d being the distance). Now given the positions of the magnets, the task to find all the points along the linear line where net force is ZERO. 

Note: Distance have to be calculated with precision of 0.0000000000001.

#### Input:
The first line of input contains an integer T denoting the no of test cases. Then T test cases follow. The second line of each test case contains an integer N. Then in the next line are N space separated values of the array M[], denoting the positions of the magnet.

#### Output:
For each test case in a new line print the space separated points having net force zero till precised two decimal places.
```
Constraints:
1<=T<=100
1<=N<=100
1<=M[]<=1000

Example:
Input:
2
2
1 2
4
0 10 20 30
Output:
1.50
3.82 15.00 26.18
```
#### Solution;
```c++
#include<bits/stdc++.h>
using namespace std;
int n;
double a[101];
double fx(double x){
    double ans = 0;
    for(int i=0;i<n;i++){
        ans += 1/(x-a[i]);
    }
    return ans;
}
double bin(double l, double r){
    double mid;
    while(r>l){
        mid = r + (l-r)*0.50;
        double val = fx(mid);
        if(abs(val) < 0.0000000000001)
        return mid;
        if(val > 0)
        l = mid;
        else r = mid;
    }
    return l;
}

int main(){
	int t;
	cin>>t;
	while(t--){
	    cin>>n;
	    for(int i=0;i<n;i++){
	        cin>>a[i];
	    }
	    for(int i=1;i<n;i++){
	        printf("%0.2f ", bin(a[i-1], a[i]));
	    }
	    cout<<endl;
	}
	return 0;
}
```
