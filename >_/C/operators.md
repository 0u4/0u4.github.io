**I AM  GOING TO TELL YOU ABOUT OPERATORS IN C**
  they are mainly 
- Unary operators
- Arithmetic operators
- Bitwise operator
- Relational operators
- Logical operators
- Conditional operators
- Assignment operators
 LET'S DISCUSS THEM IN DETAIL...
 # Unary operators
the operator which needs only one operend to work is called unary operators.
but what is operator and what is operands
3+4=7
here 3 and 4 are operands "+" plus is oprand and 7 is result..
hope you understand operator and operands

Types of unary operators:

1.unary minus(-)
2.increment(++)
3.decrement(- -)
4.NOT(!)
5.Addressof operator(&)
6.sizeof()

# Arithmetic operators
the operator which  performs mathematical operations such as addition, subtraction, multiplication, division etc called arithmetic opertors.
types

|Operator| Meaning of Operator |
| ---   | ---      |
| +      |addition or unary plus |
| -       |subtraction or unary minus|
|  *      |multiplication
| /       | division       |
| %       | remainder after division      (modulodevision)         |
 
1.as you know "+"  plus operator add two numbers,
Note that Binary operators are those operators that work with two operands.
And the turnery operators are those operators that work with three operands.
2."-" subtract operator performs subtraction
3."*" multiply(astrik) is used to multiplication
4."/" divide operator is used to divisionnn,ex:-25/5
5."%" this is The modulo operator The modulo division operator produces the remainder of an integer division. Syntax: If x and y are integers, then the expression: x % y. produces the remainder when x is divided by y.
 
# bitwise operator

| Operator|    Meaning of operators|
| ---     |    ---
| 1. &      |    Bitwise AND         |     
| 2. or      |    Bitwise OR          |
| 3. ^      |    Bitwise XOR         |
| 4. ~      |    Bitwise complement  |
| 5. <<      |    Shift left          |
| 6. >>      |    Shift right         |
      
                
bitwise and operators
The output of bitwise AND is 1 if the corresponding bits of two operands is 1. If either bit of an operand is 0, the result of corresponding bit is evaluated to 0.
example:-
  ```c
 
#include <stdio.h>
int main()
{
    int a = 12, b = 25;
    printf("Output = %d", a&b);
    return 0;
}
 ```
output will be 8
see this for better understanding
12 = 00001100 (In Binary)
25 = 00011001 (In Binary)

Bit Operation of 12 and 25
  00001100
& 00011001
  ________
  00001000  = 8 (In decimal)

2. bitwise or
Binary OR Operator copies a bit if it exists in either operand.  
example:-
(A | B) = 61, i.e., 0011 1101
3. bitwise XOR
Binary XOR Operator copies the bit if it is set in one operand but not both.
example:-
(A ^ B) = 49, i.e., 0011 0001
4. bitwise not
Binary One's Complement Operator is unary and has the effect of 'flipping' bits.  
example:-
(~A ) = ~(60), i.e,. 1100 0011
5.bitwise left shirft
<<  Binary Left Shift Operator. The left operands value is moved left by the number of bits specified by the right operand.
example:-
A << 2 = 240 i.e., 1111 0000
6.bitwise right shift
>>  Binary Right Shift Operator. The left operands value is moved right by the number of bits specified by the right operand.  
example:-
A >> 2 = 15 i.e., 0000 1111

# realtional operator
Operator  Description  Example
==      Checks if the values of two operands are equal or not. If yes, then the condition becomes true.  
example:-
(A == B) is not true.
!=      Checks if the values of two operands are equal or not. If the values are not equal, then the condition becomes true.  
example:-

(A != B) is true.
>      Checks if the value of left operand is greater than the value of right operand. If yes, then the condition becomes true.  
example:-
(A > B) is not true.
<      Checks if the value of left operand is less than the value of right operand. If yes, then the condition becomes true.  
example:-
(A < B) is true.
>=      Checks if the value of left operand is greater than or equal to the value of right operand. If yes, then the condition becomes true.  
example:-
(A >= B) is not true.
<=      Checks if the value of left operand is less than or equal to the value of right operand. If yes, then the condition becomes true.  
example:-
(A <= B) is true.

# logical operator
| Operator|    Meaning of operators|
| ---     |    ---
| 1. ==   |  equal to equal to operator |     
| 2. !=    |   not equal to operator     |
| 3. >    |    greater than operator    |
| 4. <    |    smaller than operator    |
| 5. >=    |    greater than equal to    |
| 6. <=    |    smaller than equal to    |


# conditional operator
The conditional operator is also known as a ternary operator. The conditional statements are the decision-making statements which depends upon the output of the expression.
you already know about ternory Operator ok,

 As it is understood by the name that only when there is a condition, it will be used only to understand it more easily, let us see an example. 
Example 
[uranary-operator-2nd](https://code.dcoder.tech/files/code/5ebe76274e65c356c35f6a08/uranary-operator-2nd)
 
# Assignment operators

`` Assignment operators is denoted by (=) (equal to )this symbol.
This means we are going to assign something.
Like
``c
int main ()
{
int a;
a=5;
}
``
here a is a veriable of int type and we are assigning it value 5
``
`` 
- plus equalto Operator "+=”
: This operator is combination of ‘+’ and ‘=’ operators. This operator first adds the current value of the variable on left to the value on the right and then assigns the result to the variable on the left.
Example:
(a += b) can be written as (a = a + b)
If initially value stored in a is 5. Then (a += 6) = 11.
``
``
- next we have -= Operator
``
“-=”This operator is combination of ‘-‘ and ‘=’ operators. This operator first subtracts the current value of the variable on left from the value on the right and then assigns the result to the variable on the left.
``


Example::- 
  
``
(a -= b) can be written as (a = a - b)
If initially value stored in a is 8. Then (a -= 6) = 2.
simply like +=,-=,we have *=,and /=
`` 

- multiply equalto operator

 ``
“*=”This operator is combination of ‘*’ and ‘=’ operators. This operator first multiplies the current value of the variable on left to the value on the right and then assigns the result to the variable on the left.
Example:
(a *= b) can be written as (a = a * b)
If initially value stored in a is 5. Then (a *= 6) = 30.
 ``
 
- divide equale to operator(/=)

``
“/=”This operator is combination of ‘/’ and ‘=’ operators. This operator first divides the current value of the variable on left by the value on the right and then assigns the result to the variable on the left.
Example:
(a /= b) can be written as (a = a / b)
If initially value stored in a is 6. Then (a /= 2) = 3.
`` 

# AUTHOR
[@Sant yadav](https://github.com/sant608)
source:-some from me and some from internet.
OTHER HELPFUL LINKS THAT MIGHT BE HELPFUL FOR YOU......

1.[How to use if else in c](https://code.dcoder.tech/files/article/60113fa23313006635d2c0b8/how-to-use-if-else-in-c)
2.[Loops in c](https://code.dcoder.tech/files/article/601bc82d62cf8b452bc67800/loops-in-c)
3.[A.I(artificial intelligence)](https://code.dcoder.tech/files/article/603f3cb440d0ea1344df99ad/a)
4.[Pointers in c](https://code.dcoder.tech/files/article/601f915612c1790ce40606f7/pointers-in-c)
5.[Login system to enter the main program](https://code.dcoder.tech/files/code/60505a18e83bdb06a1bbdcca/login-system-to-enter-the-main-program)
6.[Square and square root finding but with fun](https://code.dcoder.tech/files/code/6037933c1d3c7506e9d798a0/square-and-square-root-finding-but-with-fun)

if any kind of suggestion you can give me in comments.
if Any kind of spelling mistake in this article  for that please forgive me.. 🙏🙏 

> HOPE YOU LIKE THIS ARTICLE IF YOU LIKED IT PLEASE GIVE ME A STAR AND FOLLOW ME FOR MORE UPDATES see you next time!!!!!


























