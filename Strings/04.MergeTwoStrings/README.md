## Merge two strings 
Given two strings S1 and S2 as input, the task is to merge them alternatively i.e. the first character of S1 then the first character of S2 and so on till the strings end.

<b>NOTE:</b> Add the whole string if other string is empty.

#### Input:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case contains two strings S1 and S2.

#### Output:
For each test case, in a new line, print the merged string.
```
Constraints:
1 <= T <= 100
1 <= |S1|, |S2| <= 104

Example:
Input:
2
Hello Bye
abc def

Output:
HBeylelo
adbecf
```
#### Solution:
```c++
#include<iostream>
#include<string.h>

using namespace std;

void printAlternate(string s1, string s2){
    int i=0,j=0;
    while(i<s1.length() && j<s2.length()){
        cout<<s1[i++]<<s2[j++];
    }
        for(;i<s1.length();i++){
            cout<<s1[i];
        }
        for(;j<s2.length();j++){
            cout<<s2[j];
        }
   // printf("\n");
    
}

int main()
 {
	int test;
	string s1,s2;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    cin>>s1>>s2;
	    printAlternate(s1,s2);
	    printf("\n");
	}
	return 0;
}
```
