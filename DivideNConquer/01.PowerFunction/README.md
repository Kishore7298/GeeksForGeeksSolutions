## Power of Numbers
Given a number N, let the reverse of the number be R. The task is to print the output of the Expression pow(N,R), where pow function represents N raised to power R.

#### Input:
The first line of the input consists of an integer T denoting the number of test cases. Then T test cases follow. Each test case consists of a single line containing an integer N .

#### Output:
Corresponding to each test case, print in a new line, the output of the expression pow as described above.
Note: As answers can be very large, print the result modulo 100000007.
```
Constraints:
1<=T<=1000
1<=N<=78643

Example:
Input:
2
2
12
Output:
4
33235307
```
#### Solution:
```python
def power(x,y):
    if y == 0:
        return 1;
    temp = power(x,y//2);
    if(y%2 == 0):
        return temp*temp;
    else:
        return x*temp*temp;

test = int(input());
while(test):
    x = int(input());
    temp = x;
    y=0;
    while(temp > 0):
        rem = temp%10;
        y = y*10+rem;
        temp = temp//10;
    print(power(x,y)%100000007);
    test = test-1;
```
