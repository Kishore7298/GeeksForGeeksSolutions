##  Nuts and Bolts Problem 
Given a set of N nuts of different sizes and N bolts of different sizes. There is a one-one mapping between nuts and bolts. Match nuts and bolts efficiently.

Comparison of a nut to another nut or a bolt to another bolt is not allowed. It means nut can only be compared with bolt and bolt can only be compared with nut to see which one is bigger/smaller.

#### Input:
The first line contains 'T' denoting the number of testcases. Then follows description of T testcases:
Each case begins with a single positive integer N denoting the number of nuts/bolts.

Then follows the array of nuts, each element separated by a space.

And finally the bolts array, again, each element is separated by a space here.

Array of Nuts/Bolts can only consist of the following elements:

{'@', '#', '$', '%', '^', '&', '~', '*', '!'}

And no element can be repeated.

#### Output:
For each test case, output the matched array of nuts and bolts in separate lines, where each element in the array is separated by a space. Print the elements in the following order ! # $ % & * @ ^ ~ 

```
Constraints:
1<= T <= 70
1<= N <= 9


Example:

Input:
2
5
@ % $ # ^
% @ # $ ^
9
^ & % @ # * $ ~ !
~ # @ % & * $ ^ ! 

Output:
# $ % @ ^
# $ % @ ^
! # $ % & * @ ^ ~
! # $ % & * @ ^ ~
```
#### Solution:
```c++
#include<iostream>
#include<bits/stdc++.h>
using namespace std;

void nutboltmatch(char nuts[], char bolts[], int n) 
{ 
    unordered_map<char, int> hash; 
    for (int i = 0; i < n; i++) 
        hash[nuts[i]] = i; 
    for (int i = 0; i < n; i++) 
        if (hash.find(bolts[i]) != hash.end()) 
            nuts[i] = bolts[i]; 
    for (int i = 0; i < n; i++) 
        cout << nuts[i] << " "; 
    cout << endl; 
    for (int i = 0; i < n; i++) 
        cout << bolts[i] << " "; 
} 

int main()
 {
	int test;
	int n;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>n;
	    char nuts[n],bolts[n];
	    for(int j=0;j<n;j++){
	        cin>>nuts[j];
	    }
	    for(int j=0;j<n;j++){
	        cin>>bolts[j];
	    }
	    sort(nuts,nuts+n);
	    sort(bolts,bolts+n);
	    nutboltmatch(nuts,bolts,n);
	    cout<<endl;
	}
	return 0;
}
```
