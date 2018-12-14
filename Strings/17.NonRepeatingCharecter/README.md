## Non Repeating Character
Given a string S consisting of lowercase Latin Letters. Find the first non repeating character in S.

#### Input:
The first line contains T denoting the number of testcases. Then follows description of testcases.
Each case begins with a single integer N denoting the length of string. The next line contains the string S.

#### Output:
For each testcase, print the first non repeating character present in string. Print -1 if there is no non repeating character.
```
Constraints:
1 <= T <= 900
1 <= N <= 104

Example:
Input :
3
5  
hello
12
zxvczbtxyzvy
6
xxyyzz

Output :
h
c
-1
```
#### Solution:
```c++
#include<iostream>
using namespace std;
const int MAX_CHAR = 26;

char printString(string s, int n){
    int count[MAX_CHAR] ={0};
    for(int i=0;i<n;i++){
        count[s[i]-'a']++;
    }
    for(int i=0;i<n;i++){
        if(count[s[i]-'a'] == 1){
            return s[i];
        }
    }
    return '@';
}

int main()
 {
	int test,n;
	string s;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>n;
	    //cin.ignore();
	    cin>>s;
	    char m = printString(s,n);
	    if(m == '@'){
	        cout<<"-1"<<endl;
	    }else {
	        cout<<m<<endl;
	    }
	}
	return 0;
}
```
