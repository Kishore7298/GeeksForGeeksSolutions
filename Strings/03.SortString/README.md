## Sort the string in descending order

Given a string S containing only lower case alphabets, the task is to sort it in lexigraphically-descending order.

#### Input:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case contains a string S.

#### Output:
For each test case, in a new line, print the sorted string.
```
Constraints:
1 <= T <= 100
1 <= |S| <= 105

Example:
Input:
2
geeks
for
Output:
skgee
rof
```
#### Solution:
```C++
#include<bits/stdc++.h>

using namespace std;

const int MAX_CHAR=26;

void print(string s){
    int countChar[MAX_CHAR] = { 0 };
    for(int i=0;i<s.length();i++){
        countChar[s[i]-'a']++;
    }
    
    for(int i=MAX_CHAR-1;i>=0;i--){
        for(int j=0;j<countChar[i];j++){
            cout<<(char)('a'+i);
        }
    }
    printf("\n");
}

int main()
 {
	int test;
	string s;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    cin>>s;
	    print(s);
	    
	}
	return 0;
}
```
