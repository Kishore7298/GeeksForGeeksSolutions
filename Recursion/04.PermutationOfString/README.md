##  Permutations of a given string 
Given a string, print all permutations of a given string.

#### Input:
The first line of input contains an integer T, denoting the number of test cases.
Each test case contains a single string S in capital letter.

#### Output:
For each test case, print all permutations of a given string S with single space and all permutations should be in lexicographically increasing order.
```
Constraints:
1 ≤ T ≤ 10
1 ≤ size of string ≤ 5

Example:
Input:
2
ABC
ABSG
Output:
ABC ACB BAC BCA CAB CBA 
ABGS ABSG AGBS AGSB ASBG ASGB BAGS BASG BGAS BGSA BSAG BSGA GABS GASB GBAS GBSA GSAB GSBA SABG SAGB SBAG SBGA SGAB SGBA 
```
#### Solution:
```c++
#include<bits/stdc++.h>
using namespace std;

void swap(char *x, char *y){ 
    char temp; 
    temp = *x; 
    *x = *y; 
    *y = temp; 
} 

void permute(string a, int l, int r){ 
   int i; 
   if (l == r) 
     cout<<a<<" "; 
   else { 
       for (i = l; i <= r; i++){ 
          swap(a[l], a[i]);
          sort(a.begin()+l+1,a.end());
          permute(a, l+1, r); 
          swap(a[l], a[i]); 
       } 
   } 
} 

int main()
 {
	int test;
	string s;
	cin>>test;
	cin.ignore();
	for(int j=0;j<test;j++){
	    cin>>s;
	    sort(s.begin(),s.end());
	    permute(s,0,s.length()-1);
	    cout<<endl;
	}
	return 0;
}
```
