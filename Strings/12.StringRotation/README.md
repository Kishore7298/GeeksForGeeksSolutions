## Check if strings are rotations of each other or not 
Given strings s1 and s2, you need to find if s2 is a rotated version of the string s1. The strings are lowercase.

#### Input:
The first line of the input contains a single integer T, denoting the number of test cases. Then T test case follows. Each testcase contains two lines for s1 and s2.

#### Output:
For each testcase, in a new line, you need to print 1 if s2 is a rotated version of s1; else print 0.

Constraints:
1 <= T <= 100
1 <= |s1|,|s2| <= 100
```
Example:
Input:
4
geeksforgeeks
forgeeksgeeks
mightandmagic
andmagicmigth
mushroomkingdom
itsamemario
geekofgeeks
geeksgeekof
Output:
1
0
0
1

Explanation:
Ttestcase 1: s1 is geeksforgeeks, s2 is forgeeksgeeks. Clearly, s2 is a rotated version of s1 
as s2 can be obtained by left-rotating s1 by 5 units.
```
### Solution:
```c++
#include<iostream>
using namespace std;

bool isSubstring(string s, string x){
    int count=0;
    int xLength = x.length();
    for(int i=0;i<s.length()-xLength+1;i++){
        for(int j=0;j<xLength;j++){
            if(s[i+j]==x[j]){
                count++;
                if(count == xLength)
                    return true;
            } else {
                count =0;
            }
        }
    }
    return false;
}

bool isRotation(string s1, string s2){
    string temp = s1+s1;
    if(s1.length()!=s2.length())
        return false;
    if(isSubstring(temp,s2))
        return true;
    else
        return false;
    cout<<temp<<endl;
}

int main()
 {
	int test;
	string s1,s2;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>s1;
	    cin>>s2;
	    if(isRotation(s1,s2))
	        cout<<1<<endl;
	    else
	        cout<<0<<endl;
	    
	}
	return 0;
}
```
