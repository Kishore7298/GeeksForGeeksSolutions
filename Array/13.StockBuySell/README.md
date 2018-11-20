## Stock buy and sell 

The cost of stock on each day is given in an array A. Find all the days on which you buy and sell the stock so that in between those days you shouldn't have any loss.

#### Input: 
First line contains number of test cases T. Each test case contains the integer value N denoting days followed by an array of stock prices of N days. 

#### Output:
For each testcase, output all the days with profit in a single line. And if there is no profit then print "No Profit".
```
Constraints:
1 <= T <= 100
2 <= N <= 103
1 <= Ai <= 104

Example
Input:
2
7
100 180 260 310 40 535 695
10
23 13 25 29 33 19 34 45 65 67

Output:
(0 3) (4 6)
(1 4) (5 9)

Note: Output format is as follows - (buy_day sell_day) (buy_day sell_day)
For each input, output should be in a single line.
```
#### Solution:
```C++
#include<iostream>
using namespace std;

struct Interval 
{ 
	int buy; 
	int sell; 
}; 

void stockBuySell(int price[], int n) 
{ 
	if (n == 1) 
		return; 

	int count = 0; 

	Interval sol[n/2 + 1]; 

	int i = 0; 
	while (i < n-1) 
	{ 
		while ((i < n-1) && (price[i+1] <= price[i])) 
			i++; 

		if (i == n-1) 
			break; 

		sol[count].buy = i++; 

		while ((i < n) && (price[i] >= price[i-1])) 
			i++; 

		sol[count].sell = i-1; 
		count++; 
	} 
	if (count == 0) 
		printf("No Profit"); 
	else
	{ 
	for (int i = 0; i < count; i++) 
		printf("(%d %d) ", sol[i].buy, sol[i].sell); 
	} 

	return; 
} 


int main()
 {
	int test;
	int n;
	scanf("%d",&test);
	for(int i=0;i<test;i++){
	    scanf("%d",&n);
	    int a[n];
	    for(int j=0;j<n;j++){
	        scanf("%d",&a[j]);
	    }
	    stockBuySell(a,n);
	    printf("\n");
	    
	}
	return 0;
}
```
