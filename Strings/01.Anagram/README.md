## Anagram

Given two strings, check whether two given strings are anagram of each other or not. An anagram of a string is another string that contains same characters, only the order of characters can be different. For example, “act” and “tac” are anagram of each other.

#### Input:
The first line of input contains an integer T denoting the number of test cases. Each test case consist of two strings in 'lowercase' only, in a single line.

#### Output:
Print "YES" without quotes if the two strings are anagram else print "NO".
```
Constraints:
1 ≤ T ≤ 30
1 ≤ |s| ≤ 1016

Example:
Input:
2
geeksforgeeks forgeeksgeeks
allergy allergic

Output:
YES
NO
```
#### Solution:
```c++
#include<iostream>
#include<string.h>
using namespace std;
# define NO_OF_CHARS 256
bool checkAnagram(char* s1, char* s2){
    int count[NO_OF_CHARS] = {0};
    int flag=0;
    if(strlen(s1)!=strlen(s2)){
        return false;
    }
    for(int i=0;s1[i]&&s2[i];i++){
        count[s1[i]]++;
        count[s2[i]]--;
    }
    for(int i=0;i<strlen(s1);i++){
        if(count[i]){
            return false;
        }
        else {
            return true;
        }
            
    }
}

int main()
 {
	int test;
	char s1[100000],s2[100000];
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	        cin>>s1;
	        cin>>s2;
	    if(checkAnagram(s1,s2)){
	        printf("YES\n");
	    } else {
	        printf("NO\n");
	    }
	}
	return 0;
}
```
