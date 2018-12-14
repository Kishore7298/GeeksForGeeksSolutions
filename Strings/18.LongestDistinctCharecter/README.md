## Longest Distinct characters in string
Given a string S, find length of the longest substring with all distinct characters.  For example, for input "abca", the output is 3 as "abc" is the longest substring with all distinct characters.

#### Input:
The first line of input contains an integer T denoting the number of test cases.
The first line of each test case is String str.

#### Output:
Print length of smallest substring with maximum number of distinct characters.
Note: The output substring should have all distinct characters.
```
Constraints:
1 ≤ T ≤ 100
1 ≤ size of str ≤ 10000

Example:
Input:
2
abababcdefababcdab
geeksforgeeks

Output:
6
7
```
#### Solution:
```c++
#include<iostream>
#include<bits/stdc++.h>
using namespace std;

void printLength(string s){
    int arr[26]; 
    memset(arr,-1,sizeof(arr));
    int start=0;
    int end=0;
    int max1=1;
    for(int i=0;i<s.size();i++)
    {
        if(arr[s[i]-'a']==-1)
        {
            arr[s[i]-'a']=i;
            end++;
        }
        else 
        {
            if(arr[s[i]-'a']<start)
            {
                 arr[s[i]-'a']=i;
                 end++;
            }
            else
            {
                start=arr[s[i]-'a']+1;
                arr[s[i]-'a']=i;
                end++;
                
            }
        }
        max1=max(max1,(end-start));
    }
    cout<<max1<<endl;
}

int main()
 {
	int test;
	string s;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	    cin>>s;
	    printLength(s);
	}
	return 0;
}
```
