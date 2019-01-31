## Karatsuba Algorithm 
Given two binary strings that represent value of two integers, find the product of two strings. For example, if the first bit string is “1100” and second bit string is “1010”, output should be 120.

#### Input:
First line consists of T test cases. Only line of every test case consists of 2 binary strings.

#### Output:
Single line output, print the multiplied value.
```
Constraints:
1<=T<=100
1<=Length of string<=100

Example:
Input:
2
1100 01
01 01
Output:
12
1
```
#### Solution:
##### Approach 1 (easy):
```python
test = int(input());
while test:
    s = input()
    array = s.split()
    a1 = int(array[0],2)
    a2 = int(array[1],2)
    result = a1*a2
    print(result)
    test -= 1
```
