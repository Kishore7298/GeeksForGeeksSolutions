##  Add Binary Strings 
Given two binary strings s1 and s2. Print the resultant string after adding given two binary strings.

#### Input:
The first line of input contains an integer T denoting the number of test cases.
The first line of each test case contains two binary strings s1 and s2 separated by space.

#### Output:
For each test case print the resultant binary string.
```
Constraints:
1 <= T <= 70
1 <= |s1|, |s2| <= 200, where |s| represents the length of string s

Example:
Input:
2
1101 111
10 01

Output:
10100
11
```
#### Solution:
```c++
#include<iostream>
using namespace std;

void addBinary(string s, string x){
    int i = s.length()-1;
    int j = x.length()-1;
    string result = "";
    int temp=0;
    while(i>=0 || j>=0 || temp ==1){
        if(i>=0){
            temp += (s[i]-'0');
        }else {
            temp+=0;
        }
        if(j>=0){
            temp+=(x[j]-'0'); 
        }else {
            temp+=0;
        }
        result = char((temp%2)+'0') + result;
        temp = temp/2;
        i--;j--;
    }
    cout<<result<<endl;
    
}

int main()
 {
	int test;
	string s,x;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>s>>x;
	    addBinary(s,x);
	}
	return 0;
}
```
