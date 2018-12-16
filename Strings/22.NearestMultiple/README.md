## Nearest multiple of 10
Given a positive number N. The task is to round N to nearest multiple of 10. Number can be so big and can contains 1000 of digits.

#### Input:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case contains a positive number N.

#### Output:
For each test case, print the nearest multiple of 10 in new line.
```

Constraints:
1 <= T <= 100
1 <= |Number length| <= 1000

Example:
Input:
2
15
29

Output:
10
30
```
#### Solution:
##### Approach 1:
```c++
#include<iostream>
#include <boost/multiprecision/cpp_int.hpp> 
using namespace boost::multiprecision;
using namespace std;

void printRound(int1024_t s){
    int1024_t a = (s/10)*10;
    int1024_t b = a+10;
    if(s-a > b-s){
        cout<<b<<endl;
    } else {
        cout<<a<<endl;
    }
    
}

int main()
 {
	int test;
	int1024_t s;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>s;
	    printRound(s);
	}
	return 0;
}
```
##### Approach 2:
```c++
#include<bits/stdc++.h>
#define fast ios::sync_with_stdio(false);cin.tie(NULL)
#define for_i for(int i=0; i<n; i++)
#define ll long long
using namespace std;
int main()
 {
 fast;
	int t; cin>>t;
while(t--){
    string s; cin>>s;
    int n = s.length();
    if(n==1){
        if(s[0]-'0'<6) cout<<"0\n";
        else cout<<"10\n";
    }
    else if(s[n-1] - '0' <6){
        s[n-1] = '0'; 
        cout<<s<<endl;
    }
    else {
        int c=1;
        int x= n-2;
        s[n-1]='0';
        
        while(s[x]== '9'&& x>=0){
            s[x--]='0';
        }
        if(x<0){
            // cout<<"here..."<<s<<endl;
            s.insert(0, "1");  /// Prepends '1' in the string of zeroes
        }
        else s[x] = s[x]+1;
        
        cout<<s<<endl;
    }
 }
 
 return 0;
}
```
