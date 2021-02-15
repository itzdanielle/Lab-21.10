# Lab-21.10
#include <iostream>
using namespace std;

/*
_Intro to function name overloading_

Examine the code and run the program. What will happen if the user inputs 6 and 3?

Notice that the function max is overloaded. There are two different versions: one with two parameters, and another with three parameters. The version that the compiler chooses to use depends on how many arguments are provided when the function is called.

Modify the program to find the maximum of three numbers the user inputs from the keyboard (using the overloaded version of max).
*/

int max(int num1, int num2);
int max(int num1, int num2, int num3);

int main() {
  int input1, input2, input3;
  cout << "Enter the first number: ";
  cin >> input1;
  cout << "Enter the second number: ";
  cin >> input2;
  cout << "Enter the third number: ";
  cin >> input3;
  cout << "The max is " << max(input1, input2, input3) << endl;
}

int max(int num1, int num2)
{
  if (num1 > num2)
    return num1;
  else
    return num2;
}

int max(int num1, int num2, int num3)
{
  int max12 = max(num1, num2);
  int max13 = max (num2, num3);
  int max23 = max(num1, num3);
  if ((max12 > max23) || (max12 > max13)) {
    return max12;
  }
  else if (max23 > max13) {
    return max23;
  }
  else 
  return max13;
}
