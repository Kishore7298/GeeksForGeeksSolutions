## Check if two strings are k-anagrams or not

Given two strings of lowercase alphabets and a value K, your task is to complete the given function which tells if  two strings are K-anagrams of each other or not.
Two strings are called K-anagrams if both of the below conditions are true.
1. Both have same number of characters.
2. Two strings can become anagram by changing at most K characters in a string.

#### Input Format:
The first line of input contains an integer T denoting the no of test cases. Then T test cases follow. The first line of input contains two Strings Str1 and Str2. And next line contains an integer K, which denotes number of characters can be replaced.

#### Output Format:
For each testcase, in a new line, print the respective output.

#### Your Task:
Since this is a function problem, you don't need to take any input. Just complete the given function areKAnagrams that returns true if the strings can be turned into K-anagrams, else return false.
```
Constraints:
1 <= T <= 100
1 <= K <= |length of String|

Example:
Input:
1
fodr gork
2
Output:
1

Explanation:
Testcase1: change fd to gk
```
### Solution:
```c++
bool areKAnagrams(string str1, string str2, int k)
{
    int count[MAX_CHAR] = {0};
    if(str1.length()!=str2.length()){
        return false;
    }
    for(int i=0;i<str1.length();i++){
        count[str1[i]-'a']++;
    }
    int strCount=0;
    for(int i=0;i<str1.length();i++){
        if(count[str2[i]-'a']>0){
            count[str2[i]-'a']--;
        } else {
            strCount++;
            if(strCount > k)
                return false;
        }
    }
    return true;
}
```
