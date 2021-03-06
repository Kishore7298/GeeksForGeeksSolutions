##  Multiply two strings 
Given two numbers as stings s1 and s2 your task is to multiply them. You are required to complete the function multiplyStrings which takes two strings s1 and s2 as its only argument and returns their product as strings.

#### Input:
The first line of input contains an integer T denoting the no of test cases. Then T test cases follow . Each test case contains two strings s1 and s2 .

#### Output:
For each test case in a new line the output will be a string denoting the product of the two strings s1 and s2.
```
Constraints:
1 <= T <= 100
1 <= length of s1 and s2 <= 103

Example(To be used only for expected output) :
Input:
2
33 2
11 23
Output:
66
253
```
<b>Note:</b>The Input/Ouput format and Example given are used for system's internal purpose, and should be used by a user for Expected Output only. As it is a function problem, hence a user should not read any input from stdin/console. The task is to complete the function specified, and not to write the full code.
#### Solution:
```c++
string multiplyStrings(string num1, string num2) {
   int sign = 1;
    
    if (num1[0] == '-') {
       sign = sign * (-1);
       num1.erase(num1.begin());
   }
   
   if (num2[0] == '-') {
       sign = sign * (-1);
       num2.erase(num2.begin());
   }
   
    int n1 = num1.size();
    int n2 = num2.size();
    if (n1 == 0 || n2 == 0)
       return "0";
 
    vector<int> result(n1 + n2, 0);
 
    int i_n1 = 0; 
    int i_n2 = 0; 
 
    for (int i=n1-1; i>=0; i--)
    {
        int carry = 0;
        int n1 = num1[i] - '0';
 
        i_n2 = 0; 
         
        for (int j=n2-1; j>=0; j--)
        {
        
            int n2 = num2[j] - '0';
 
            int sum = n1*n2 + result[i_n1 + i_n2] + carry;
 
            carry = sum/10;
 
            result[i_n1 + i_n2] = sum % 10;
 
            i_n2++;
        }
 
        if (carry > 0)
            result[i_n1 + i_n2] += carry;
 
        i_n1++;
    }
 
    int i = result.size() - 1;
    while (i>=0 && result[i] == 0)
       i--;
 
    if (i == -1)
       return "0";
 
    string s = "";
    while (i >= 0)
        s += std::to_string(result[i--]);
        
    if (sign == -1)
        s.insert(s.begin(), '-');
 
    return s;
}
```
