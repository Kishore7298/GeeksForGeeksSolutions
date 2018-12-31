##  Recursively remove all adjacent duplicates 
Given a string s, recursively remove adjacent duplicate characters from the string s. The output string should not have any adjacent duplicates.
 
#### Input:
The first line of input contains an integer T, denoting the no of test cases. Then T test cases follow. Each test case contains a string str.

#### Output:
For each test case, print a new line containing the resulting string.
```
Constraints:
1<=T<=100
1<=Length of string<=50

Example:
Input:
2
geeksforgeek
acaaabbbacdddd

Output:
gksforgk
acac
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

char* removeUtil(char *str, char *last_removed) { 
	if (str[0] == '\0' || str[1] == '\0') 
		return str; 
	if (str[0] == str[1]) { 
		*last_removed = str[0]; 
		while (str[1] && str[0] == str[1]) 
			str++; 
		str++; 
		return removeUtil(str, last_removed); 
	} 
	char* rem_str = removeUtil(str+1, last_removed); 
	if (rem_str[0] && rem_str[0] == str[0]) { 
		*last_removed = str[0]; 
		return (rem_str+1); 
	} 
	if (rem_str[0] == '\0' && *last_removed == str[0]) 
		return rem_str; 
	rem_str--; 
	rem_str[0] = str[0]; 
	return rem_str; 
} 

char *remove(char *str) 
{ 
	char last_removed = '\0'; 
	return removeUtil(str, &last_removed); 
} 

int main()
 {
	int test;
	char s[52];
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>s;
	    cout<<remove(s)<<endl;
	    
	}
	return 0;
}
```
