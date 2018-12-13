## Uncommon characters 
Find and print the uncommon characters of the two given strings S1 and S2. Here uncommon character means that either the character is present in one string or it is present in other string but not in both. The strings contains only lowercase characters and can contain duplicates.

#### Input:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case contains two strings in two subsequent lines.

#### Output:
For each testcase, in a new line, print the uncommon characters of the two given strings in sorted order.

Constraints:
1 <= T <= 100
1 <= |S1|, |S2| <= 105
```
Example:
Input:
1
characters
alphabets
Output:
bclpr
```
#### Solutions:
```c++
#include<iostream>
using namespace std;

const int MAX_CHAR = 26; 

void printString(string s1, string s2){
    int present[MAX_CHAR]= {0}; 
    int l1 = s1.size();
    int l2 = s2.size();
    for(int i=0;i<l1;i++){
        present[s1[i]-'a'] =1;
    }
    for(int j=0;j<l2;j++){
        if(present[s2[j]-'a']==1 || present[s2[j]-'a']==-1){
            present[s2[j]-'a']=-1;
        } else {
            present[s2[j]-'a']=2;
        }
    }
    for(int i=0;i<MAX_CHAR;i++){
        if(present[i]==1 || present[i]==2)
            cout<<char(i+'a');
    }
    cout<<endl;
    
}

int main()
 {
	int test;
	string s1, s2;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>s1;
	    cin>>s2;
	    printString(s1,s2);
	}
	return 0;
}
```
