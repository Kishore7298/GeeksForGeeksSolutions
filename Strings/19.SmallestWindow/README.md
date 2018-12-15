## Smallest window in a string containing all the characters of another string
Given a string S and text t. Output the smallest window in the string having all characters of the text. Both the string and text contains small case letters.

#### Input:
First line contains T , the number of test cases and each test contains 2 lines having a string S and t.

#### Output:
Output the smallest window of the string containing all the characters of the text. If such window doesn`t exist or this task can not be done then print -1.
```
Constraints:
1 <= T <= 100
1 <= N, X <= 1000

Example:
Input:
2
timetopractice
toc
zoomlazapzo
oza

Output:
toprac
apzo
```
#### Solution:
```c++
#include<iostream>
#include<limits.h>
using namespace std;

const int no_of_chars = 256;

string findSubString(string str, string pat) 
{ 
	int len1 = str.length(); 
	int len2 = pat.length(); 
	if (len1 < len2){ 
		cout << "-1"; 
		return ""; 
	} 
	int hash_pat[no_of_chars] = {0}; 
	int hash_str[no_of_chars] = {0}; 
	for (int i = 0; i < len2; i++) 
		hash_pat[pat[i]]++; 
	int start = 0, start_index = -1, min_len = INT_MAX; 
	int count = 0;
	for (int j = 0; j < len1 ; j++) 
	{ 
		hash_str[str[j]]++; 
		
		if (hash_pat[str[j]] != 0 && 
			hash_str[str[j]] <= hash_pat[str[j]]) 
			count++; 
		if (count == len2) { 
			while ( hash_str[str[start]] > hash_pat[str[start]] || hash_pat[str[start]] == 0){ 
				if (hash_str[str[start]] > hash_pat[str[start]]) 
					hash_str[str[start]]--; 
				start++; 
			} 
			int len_window = j - start + 1; 
			if (min_len > len_window){ 
				min_len = len_window; 
				start_index = start; 
			} 
		} 
	} 
	if (start_index == -1){ 
	    cout << "-1"; 
	    return ""; 
	} 
	return str.substr(start_index, min_len); 
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
	    cout<<findSubString(s,x)<<endl;
	}
	return 0;
}
```
