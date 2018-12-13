##  Check for subsequence 
Given two strings A and B, find if A is a subsequence of B.

#### Input:
The first line of input contains an integer T denoting the no of test cases. Then T test cases follow. Each test case contains two space separated strings A and B.

#### Output:
For each test case, in a new line, print 1 if a is sub-sequences of b else print 0.
```
Constraints:
1 <= T <= 900
1<= |A|,|B| <=104

Example:
Input:
2
AXY YADXCP
gksrek geeksforgeeks

Output:
0
1
```
#### Explanation:
<b>Testcase1:</b>
Input: A = "axy", B = "yadxcp"
Output: 0 (A is not a subsequence of B)  
<b>Testcase2:</b>
Input: A = "gksrek", B = "geeksforgeeks"
Output: 1 (str1 is a subsequence of str2)

### Solution:
```c++
#include<iostream>
using namespace std;

bool checkString(string s, string x){
    int j=0;
    for(int i=0;i<s.length();i++){
        if(s[i]==x[j]){
            j++;
            if(j == x.length())
                return true;
        }
    }
    return false;
}

int main()
 {
	int test;
	string s,x;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>s;
	    cin>>x;
	    if(checkString(x,s))
	        cout<<"1"<<endl;
	    else
	        cout<<"0"<<endl;
	}
	return 0;
}
```
