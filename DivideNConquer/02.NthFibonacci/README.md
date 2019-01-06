##  The Nth Fibonnaci 
Given a positive integer N, write a program to find the last digit of the N'th term from the Fibonnaci series and print it.

#### Input
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. 
The first line of each test case contains a positive integer N.


#### Output
Print out the last digit of N'th Fibonacci number.

```
Constraints
1 <= T <= 100
0 <   N  <= 1000

Examples 

Input
4
1
5
14
300

Output
1
5
7
0
```
#### Solution:
```python
def fibonacci(n): 
    a = 0
    b = 1
    if n < 0: 
        print("Incorrect input") 
    elif n == 0: 
        return a 
    elif n == 1: 
        return b 
    else: 
        for i in range(2,n+1): 
            c = a + b 
            a = b 
            b = c 
        return b  
test = int(input());
while(test):
    n = int(input());
    print(fibonacci(n)%10);
    test -= 1;
```
