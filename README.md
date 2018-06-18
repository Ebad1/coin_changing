//          coin_changing
//              1st repository
#include<stdio.h>
#include<iostream>
using namespace std;
void coin_change(int c[], int a, int b){
	cout << "Greedy's solution:\n{";
	int i = b;
	while (a != 0){
		if (c[i] <= a){
			cout << c[i];
			a = a - c[i];
			if (a > 0){
				cout << ",";
			}
		}
		else if (c[i] > a){
			i--;
			if (c[i] < a){
				cout << c[i] << ",";
				a = a - c[i];


			}

		}
	}
	cout << "}\n";
}
int main(){
	int temp;
	cout << "Enter the value that need to be change in coins: ";//Value that you want in coins eg: 140$
	int a; cin >> a;
	cout << "Enter the no of coins you have: ";//number of coins you have of different values to change that 140$ in coins.
	int b; cin >> b;
	int* c = new int[b];
	for (int i = 1; i <= b; i++)
	{
		cout << "Enter value of " << i << " coin: ";//specific values for those coins that you have
		cin >> c[i];
	}
	coin_change(c, a, b);
}
