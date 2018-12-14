## Find first repeated character 
Given a string S. The task is to find the first repeated character in it. We need to find the character that occurs more than once and whose index of first occurrence is smallest. S contains only lowercase letters.
#### Input:
The first line of input contains an integer T denoting the no of test cases. Then T test cases follow. Each test case contains a string S.

#### Output:
For each test case in a new line print the first repeating character in the string. If no such character exist print -1.
```
Constraints:
1 <= T <= 100
1 <= |S| <=104

Example:
Input:
2
geeksforgeeks
hellogeeks

Output:
e
l
```
#### Solution:
```c++
#include<iostream>
using namespace std;

char printRepeating(string s){
    int count[26]={0};
    for(int i=0;i<s.length();i++){
        count[s[i]-'a']++;
        if(count[s[i]-'a']>1){
            return s[i];
            break;
        }
    }
    return '//';
}

int main()
 {
	int test;
	string s;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>s;
	    if(printRepeating(s) != '/'){
	       char m = printRepeating(s);
	        cout<<m<<endl; 
	    } else {
	        cout<<"-1"<<endl;
	    }
	}
	return 0;
}
```
