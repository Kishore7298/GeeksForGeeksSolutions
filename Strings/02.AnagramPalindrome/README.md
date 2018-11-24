## Anagram Palindrome 

Given a string S, Check if characters of the given string can be rearranged to form a palindrome. 
For example characters of “geeksogeeks” can be rearranged to form a palindrome “geeksoskeeg”, but characters of “geeksforgeeks” cannot be rearranged to form a palindrome.

#### Input:
First line consists of integer T  denoting the number of test cases. T testcases follow. For each testcase there are one line of input containing string S.

#### Output:
For each testcase, in a new line, print "Yes" if is possible to make it a palindrome, else "No".
```
Constraints:
1 <= T <= 100
1 <= |S| <= 1000

Example:
Input:
2
geeksogeeks
geeksforgeeks
Output:
Yes
No
```

#### Solution:
```C++
#include<iostream>
#include<string.h>
#define NO_OF_CHAR 256
using namespace std;

bool canFormPalindrome(char *s){
    int count[NO_OF_CHAR] = {0};
    int odd=0;
    for(int i=0;i<strlen(s);i++){
        count[s[i]]++;
    }
    for(int i=0;i<NO_OF_CHAR;i++){
        if(count[i] & 1){
            odd++;
        }
    }
    if(odd>1)
        return false;
    return true;
}

int main()
 {
	int test;
	char s[1000];
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    cin>>s;
	    if(canFormPalindrome(s)){
	        printf("Yes\n");
	    } else {
	        printf("No\n");
	    }
	}
	return 0;
}
```
