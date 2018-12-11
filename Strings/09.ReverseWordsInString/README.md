#  Reverse words in a given string 
Given a String of length S, reverse the whole string without reversing the individual words in it. Words are separated by dots.

#### Input:
The first line contains T denoting the number of testcases. T testcases follow. Each case contains a string S containing characters.

#### Output:
For each test case, in a new line, output a single line containing the reversed String.
```
Constraints:
1 <= T <= 100
1 <= |S| <= 2000

Example:
Input:
2
i.like.this.program.very.much
pqr.mno

Output:
much.very.program.this.like.i
mno.pqr
```
### Solutions:
```c++
#include<iostream>
#include <bits/stdc++.h>
using namespace std;

void reverseSentence(string s){
    int i=0;
    unsigned int j;
    for(j=0;j<=s.length();j++){
        if(s[j]=='.'){
            reverse(&s[i],&s[j]);
            i=j+1;
        } else
            continue;
    }
    reverse(&s[i],&s[s.length()]);
    cout<<s<<endl;
}

int main()
 {
	int test;
	string s;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>s;
    reverse(s.begin(),s.end());
    reverseSentence(s);
	}
	return 0;
}

```
