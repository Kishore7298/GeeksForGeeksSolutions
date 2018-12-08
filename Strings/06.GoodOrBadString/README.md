## Good or Bad string 
In this problem, a String S is composed of lowercase alphabets and wildcard characters i.e. '?'. Here, '?' can be replaced by any of the lowercase alphabets. Now you have to classify the given String on the basis of following rules:

If there are more than 3 consonants together or more than 5 vowels together, the String is considered to be "BAD". A String is considered "GOOD" only if it is not “BAD”.

<b>NOTE:</b> String is considered as "BAD" if the above condition is satisfied even once. Else it is "GOOD" and the task is to make the string "BAD".

#### Input:
The first line consists of an integer T i.e number of test cases. T testcases follow. The first and only line of each test case consists of a string S. 

#### Output:
For each testcase, in a new line, print "1"  if string is GOOD, else print "0".
```
Constraints: 
1 <= T <= 100
1 <= |S| <= 100

Example:
Input:
2
aeioup??
bcdaeiou??
Output:
1
0
```
#### Solution:
```c++
#include<iostream>
using namespace std;

bool checkString(string s){
    int vCount=0;
    int cCount=0;
    for(int i=0;i<s.length();i++){
        if(s[i]=='a'|| s[i]=='e'||s[i]=='i'||s[i]=='o'||s[i]=='u'){
            vCount++;
            cCount=0;
            if(vCount > 5){
                return true;
            }
        } else {
            if(s[i]=='?'){
                vCount++;
                cCount++;
            } else {
                vCount=0;
                cCount++;
                if(cCount>3){
                    return true;
                }
            }
        }
    }
    return false;
}

int main()
 {
	int test;
	string s;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    cin>>s;
	    if(checkString(s)){
	        printf("0\n");
	    } else {
	        printf("1\n");
	    }
	    
	}
	return 0;
}
```
