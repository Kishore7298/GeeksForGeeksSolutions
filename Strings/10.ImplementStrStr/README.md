## Implement strstr 
Your task is to implement the function strstr. The function takes two strings as arguments (s,x) and  locates the occurrence of the string x in the string s. The function returns and integer denoting the first occurrence of the string x in s.

#### Input Format:
The first line of input contains an integer T denoting the no of test cases . Then T test cases follow. The first line of each test case contains two strings s and x.

#### Output Format:
For each test case, in a new line, output will be an integer denoting the first occurrence of the x in the string s. Return -1 if no match found.

#### Your Task:
Since this is a function problem, you don't have to take any input. Just complete the strstr function.
```
Constraints:
1 <= T <= 100
1<= |s|,|x| <= 1000

Example:
Input
2
GeeksForGeeks Fr
GeeksForGeeks For
Output
-1
5

``` 

<b>Note:</b>The Input/Ouput format and Example given are used for system's internal purpose, and should be used by a user for Expected Output only. As it is a function problem, hence a user should not read any input from stdin/console. The task is to complete the function specified, and not to write the full code.

#### Solution:
```c++
int strstr(string s, string x)
{
    int counts =0;
    for(int i=0;i<s.length();i++){
        for(int j=0;j<x.length();j++){
            if(s[i+j]==x[j]){
                counts++;
                if(counts==x.length());
                    return i;
            } else {
                counts =0;
                break;
            }
        }
    }
    return -1;
}

```
