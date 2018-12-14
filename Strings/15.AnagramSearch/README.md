## Anagram of String 
Given two strings S1 and S2 in lowercase, the task is to make them anagram. The only allowed operation is to remove a character from any string. Find minimum number of characters to be deleted to make both the strings anagram. If two strings contains same data set in any order then strings are called Anagrams.

#### Input Format:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case consists of 2 strings to make the anagrams.

#### Output Format:
For each testcase, in a new line, output the minimum number of characters to be deleted to make both the strings anagram.

#### Your Task:
Since this is a function problem, you don't need to take any input. Just complete the provided function.
```
Constraints:
1 <= T <= 100
1 <= |S1|, |S2| <= 105

Example:
Input:
2
bcadeh
hea
cddgk
gcd
Output:
3
2
```
##### Solution:
```c++
int remAnagram(string str1, string str2)
{
    int count1[26] = {0};
    int count2[26] = {0};
    int result=0;
    for(int i=0;i<str1.length();i++){
        count1[str1[i]-'a']++;
    }
    for(int i=0;i<str2.length();i++){
        count2[str2[i]-'a']++;
    }
    for(int i=0;i<26;i++){
        result += abs(count1[i]-count2[i]);
    }
    return result;
}
```
