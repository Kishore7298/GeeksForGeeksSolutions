## Handshakes
We have N persons sitting on a round table. Any person can do a handshake with any other person.
```
    1
2        3
    4
```
Handshake with 2-3 and 1-4 will cause cross.

In how many ways these N people can make handshakes so that no two handshakes crosses each other. N would be even. 

For example, in above diagram, there are two non-crossing ways to handshake {{1, 2}, {3, 4}} and {{1, 3}, {2, 4}}.

#### Input:

The first line of input contains an integer T denoting the number of test cases.
The first line of each test case is N.

#### Output:

Print number of ways.
```
Constraints:

1 ≤ T ≤ 20
2 ≤ N ≤ 30

Example:

Input:
2
2
8

Output:
1
14
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

unsigned long int catalan(unsigned long int n) 
{ 
    if (n <= 1) return 1; 
    unsigned long int res = 0; 
    for (int i=0; i<n; i++) 
        res += catalan(i)*catalan(n-i-1); 
  
    return res; 
} 

int main()
 {
	int test;
	unsigned long int n;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>n;
	    cout<<catalan(n/2)<<endl;
	}
	return 0;
}
```
