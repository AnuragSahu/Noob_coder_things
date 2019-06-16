---
title: "Progress on the First day."
---

This post will be about the progress I made in the First day that is on 12 Jun 19,

I started searching the C++ tutorials for Competitive Coding, I landed on the Introductory tutorials for Competitive coding on CODECHEF. https://www.codechef.com/ioi/basics, <br>

It s a great Reseource to start with, I did the First part of the tutorials, Basic Number theory,

Learning from First Day:-
 - Calculation of modulo
{% highlight ruby %}

#include <iostream>
using namespace std;

int mult(int a,int b,int c){
        if(b==1){
                return ((a%c)*(2%c))%c;
        }
        else{
                return ((a%c)*(mult(a,b-1,c)%c))%c;
        }
}

int main()
{
        int a = 10105;
        int b = 123456;
        int bas = 2;
        int md = 10000;
        int total=1;
        int i,j;
        int res = mult(2,a-1,md);
        int res1 = mult(2,b-1,md);
        res = (res+res1)%md;
        cout << res << "\n";
        return 0;
}


{% endhighlight %}

- Checking if a number is prime or not.

{% highlight ruby %}

#include<iostream>
using namespace std;
int main(){
	int number;
	int arr[100000] = {};
	cout << "Enter the numbers(<100000): ";
	cin >> number;
	arr[0] = 2;
	// building the table
	int till = 1;
	for(int i=3;i<=number;i++){
		bool flag = false;
		for (int j = 0;j<till;j++)
			if(i%arr[j] == 0){
				flag = true;
				break;
		}
		if(flag == false){
			arr[till++] = i;
		}
	}
// Checking the if the number is prime
	if(number == arr[till-1]){ cout << "YES\n";}
	else { cout << "NO\n";}
	return 0;
}

{% endhighlight %}

- Calculation of (N-1)! % N
{% highlight ruby %}

#include <iostream>
using namespace std;

int factorial(int number){
	if(number == 1){
		return 1;
	}
	else return number * factorial(number-1);
}

int main()
{
	int number;
	cout << "Enter the number: ";
	cin >> number;
	cout << factorial(number -1) % number << "\n";
    return 0;
}

{% endhighlight %}

- Important Formulas
	- (a+b) mod c = ((a mod c) + (b mod c)) mod c
	- (a*b) mod c = ((a mod c) * (b mod c)) mod c
	- (a-b) mod c = ((a mod c) - (b mod c)) mod c
