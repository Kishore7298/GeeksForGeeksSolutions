## URLify a given string
Write a method to replace all the spaces in a string S with ‘%20’. You may assume that the string has sufficient space (or allocated memory) at the end to hold the additional characters,

#### Input:
The first line of input contains an integer T denoting the number of test cases. The T test cases follow. Each test case contains two lines of input. The first line contains a string S. The next line contains an integer K that denotes the length of the S with whitespace included.

#### Output:
For each testcase, in a new line, print the string with spaces replaced by "%20".
```
Constraints:
1 <= T <= 1000
1 <= |S|+ K <= 1000

Example:
Input:
2
Mr John Smith
13
Mr Benedict Cumberbatch  
25

Output:
"Mr%20John%20Smith"
"Mr%20Benedict%20Cumberbatch
```
<b>Explanation:</b>
Here in the second case 25 means that there are 25 characters taken into input. While the length of the string is 23 , it means that there are 2 extra spaces at the end which needs to be removed and is contained in input. So the output should be those 23 characters with 2 extra spaces removed and spaces between word replaced with %20.

#### Solution:

##### Approach 1:
```c++
#include<iostream>
using namespace std;

void Urlify(string s, int strLength){
    for(int i=0;s[i];i++){
        if(s[i]==' '){
            cout<<"%20";
        } else {
            cout<<s[i];
        }
    }
    cout<<endl;
}

int main()
 {
	int test;
	string s;
	int count;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	   getline(cin,s);
	   cin>>count;
	   cin.ignore();
	   Urlify(s,count);
	   //for(int j=0;j<c;j++){
	   //    printf("%d",s[j]);
	   //}

	}
	return 0;
}

```

##### Approach 2:(Not working)
```c++
#include<iostream>
using namespace std;

int Urlify(string s, int strLength){
    int spaceCount=0;
    int i;
    for(i=0;s[i];i++){
        if(s[i] == ' '){
            spaceCount++;
        }
    }
    while(s[i-1]==' '){
        spaceCount--;
        i--;
    }
    int new_length=i+(2*spaceCount)+1;
    int index = new_length-1;
    s[index--]='\0';
    for(int j=index;j>=0;j--){
        if(s[j]==' '){
            s[index]='0';
            s[index-1]='2';
            s[index-2]='%';
            index=index-3;
        } else {
            s[index--]=s[j];
        }
    }
    return new_length;
}

int main()
 {
	int test;
	string s;
	int count;
	cin>>test;
	cin.ignore();
	for(int i=0;i<test;i++){
	   getline(cin,s);
	   cin>>count;
	   cin.ignore();
	   int c= Urlify(s,count);
	   for(int j=0;j<c;j++){
	       printf("%c",s[j]);
	   }

	}
	return 0;
}

```
