#  Extract Maximum 

You have been given an alphanumeric string S, extract maximum numeric value from that string. Alphabets will only be in lower case.

### Input:
The first line contains a single integer T i.e. the number of test cases. T testcases follow. The first and only line consists of a String S.

### Output: 
For each testcase, in a new line, print the Maximum number extracted from the string S.
```
Constraints:
1 <= T <= 100
2 <= |S| <= 200

Example:
Input:
3
100klh564abc365bg
abvhd9sdnkjdfs
abchsd0sdhs
Output:
564
9
0
```
<b>Explanation:</b>
Test Case 1: The maximum number found in the string is "564". 
### Solution:
```c++
#include<iostream>
#include<limits.h>
#include<bits/stdc++.h> 
using namespace std;

void printMaxNumber(string s){
    int max=INT_MIN;
    int j=0;
    int num=0;
    char temp[100];
    for(int i=0;i<s.length();i++){
        if(s[i]>=48 && s[i]<=57 ){
            num = (num*10)+(s[i]-'0');
        }else {
            if(max<num){
                max=num;
                num=0;
            } else{
                num=0;
            }
        }
    }
    if(max<num)
        max=num;
  
    cout<<max<<endl;
}

int main()
 {
	int test;
	string s;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>s;
	    printMaxNumber(s);
	}
	return 0;
}
```
