This is the first part.....
# what is pointer
1.Define:-
 `
it is a variable that contains adress of the
another variable.
`

2. Declaring a Pointer
```
Like variables, pointers in C programming have to be declared before they can be used in your program. Pointers can be named anything you want as long as they obey C's naming rules. A pointer declaration has the following form.
```
syntax:-
```
data_type * pointer_variable_name;
```
Here,

data_type is the pointer's base type of C's variable types and indicates the type of the variable that the pointer points to.
The asterisk (*: the same asterisk used for multiplication) which is indirection operator, declares a pointer.

3. some points about `*`
we use * star symbol to represent that it is. apointer variable
- `*` it is also called dereferencing operator
- `*` it is also called indirection operator
- `*` is unary operator
- `*` it takes adress as an argument
- `*` returns the content/container whose adress its argument.
- we cannot use `&` in left side and assign a value like this(it will give error).
- reason:- we cannot store anything in `&` of access `&` of x is not a variable it is the way to represent address of a block x
```c
#include<stdio.h>

int main()
{
  int x=5;
  &x=7 // it will give error
}
```
```
OUTPUT IS ERROR
```


4. pointer consumes always 2 bytes in memory
EXAMPLE:-
  ```c
 int man()
 {
   int *p,s; // look at * symbol it shows that pointer variable p is not an ordinary variable 
   printf("enter a number\n");
   scanf("%d",&s);
   *p=&s;
   printf("%d",*p);
 }
 ```
 
**output will be the adress of s**
 
 here see this for better understanding 
 [pointer](https://code.dcoder.tech/files/code/603de70165ac470b988933a3/pointer)
 
 
5. "&" this sign represent the adress as you use to take input.  
6.
NULL Pointers
It is always a good practice to assign a NULL value to a pointer variable in case you do not have an exact address to be assigned. This is done at the time of variable declaration. A pointer that is assigned NULL is called a null pointer.

The NULL pointer is a constant with a value of zero defined in several standard libraries. Consider the following program −

demo
```c
#include <stdio.h>

int main () {

   int  *ptr = NULL;

   printf("The value of ptr is : %x\n", ptr  );
 
   return 0;
}
```
When the above code is compiled and executed, it produces the following result −

The value of ptr is 0
In most of the operating systems, programs are not permitted to access memory at address 0 because that memory is reserved by the operating system. However, the memory address 0 has special significance; it signals that the pointer is not intended to point to an accessible memory location. But by convention, if a pointer contains the null (zero) value, it is assumed to point to nothing.

To check for a null pointer, you can use an 'if' statement as follows −
```c
if(ptr)     /* succeeds if p is not null */
if(!ptr)    /* succeeds if p is null */
  ```
Pointers in Detail
Pointers have many but easy concepts and they are very important to C programming. The following important pointer concepts should be clear to any C programmer −

Sr.No.  Concept & Description

- Pointer arithmetic
There are four arithmetic operators that can be used in pointers: ++, --, +, -


- Array of pointers
You can define arrays to hold a number of pointers.


- Pointer to pointer
C allows you to have pointer on a pointer and so on.


- Passing pointers to functions in C
Passing an argument by reference or by address enable the passed argument to be changed in the calling function by the called function.


- Return pointer from functions in C
C allows a function to return a pointer to the local variable, static variable, and dynamically allocated memory as well.



other helpful links
1.loops in c
[Loops in c](https://code.dcoder.tech/files/article/601bc82d62cf8b452bc67800/loops-in-c)
2.if else in c
[How to use if else in c](https://code.dcoder.tech/files/article/60113fa23313006635d2c0b8/how-to-use-if-else-in-c)
3.square and squre root find
[Square and square root finding but with fun](https://code.dcoder.tech/files/code/6037933c1d3c7506e9d798a0/square-and-square-root-finding-but-with-fun)

##  information:- other parts of pointer is remain to came,stay tuned.
**and don't forget to follow  me for more updates if you like it and star this article and if you understand comment me..thanks**










Let's know about more in pointer,but if you didn't saw the first part then please see it first here,
[Pointers in c](https://code.dcoder.tech/files/article/601f915612c1790ce40606f7/pointers-in-c)

# 1 Types of pointer in c
1. void pointer
2. Null pointer
3. wild pointer
4. dangling pointer

> let's know about them one by one 

**Void Pointer**
- A void pointer is a pointer that is no data type associated with it .
- A void pointer can easily typecast to any pointer type .
- A simple language it is a general purpose pointer variable.

Example:-
  ```c
  #include<stdio.h>
int main()
{

  int x=10;
  char y=x;
  void *p=&x; // void pointer stores adress of int x
  p=&y; // void pointer now hoods adress of char y
  return 0;
  }
  ```
more code:-
```c
#include<stdio.h>
int main()
{
    int a[2] = {1, 2};
    void *ptr = &a;
    ptr = ptr + sizeof(int);
    printf("%d", *(int *)ptr);
    return 0;
}
```

> Use of void pointer
- In D.M.A calloc() and malloc() returns void type pointer memory of any data type. This is because these pointers can be typecasted to any pointer type
- This allows these D.M functions to be used to allocate memory of any data type.THis is because thses pointers can be typecasted to any pointer type

More in Void Pointer
- It is not possibile to dereference void pointer.
- Pointer arithmetic is not allowed in `c standereds` with void pointers.
- Hence,it is not recommended to use pointer arithmetic with void pointer.
    
# Null Pointer
Null pointer is a pointer which has a value reserved for indicating that the pointer or reference does not refer to a valid object.

- A null pointer guarented to compare equal to any pointer that points to a valid objects.
- dereferencing a Null Pointer is undefined behavior in C, and a conforming implementation is allowed to assume that any pointer that is dereferenced is not Null.
- Null pointer is a specific pointer which is mentioneeed in C standereds and it has specific purpose.

More in Null pointer
- A null pointer is a pointer that points to a null(nothing).
- A null points should not be dereferenced.
- A check must be run by the c programmer to know whether a pointer is null before dereferencing it.
- A Null Macro is defined as ((void*)o) in header file of most of the c compiler implimentation.
- Null pointer is uninitialized pointerAn uninitialized pointer contains an undefined value.
- A null pointer straw a defined value,which is the one decided by the environment to not be a valid memory adress for any object.
- A null pointer is void pointer-null pointer is a value as void pointer is a type.
let's look its syntax:- 
```c
# include <stdio.h>
int main()
{
    int x=10;
    int *p=NULL; // NULL should be written in capital as i written
    p=&x;
}
```
Full code 
```c
#include <stdio.h>
int main()
{
 int *i, *j;
 int *ii = NULL, *jj = NULL;
 if(i == j)
 {
  printf("This might get printed if both i and j are same by chance.");
 }
 if(ii == jj)
 {
  printf("This is always printed coz ii and jj are same.");
 }
 return 0;
}
```

Uses of NUll Pointer

1. To initialize a pointer variable in case where pointer variable has not been assigned any valid adress yet.
2. TO check for legitimate adress location before accessing any pointer variable.
3. By doing so, we can perform adress location before accessing any points variable.
4. Ex of such error handling can be dereference pointer variable only if it's not null.
5. To poss a null Pointer to a function argument when we don't want to pass any valid memory adress.

# Wild Pointer
uninitialized pointers are know as wild pointer.
- These pointers point to some arbitary location in memory and may cause a program to crash or behave badly.
- dereferencing wild pointer initialize unused pointers to Null.
see the syntax;-
```c
# include <stdio.h>
int main()
{
    int a =3;  // here ptr is a wild pointer
    int *ptr; // here it is no longer wild
    ptr=&a;

}
```  
more code:-
```c
#include <stdio.h>
int main()
{
   int *p = (int *)malloc(sizeof(int));
  *p = 12; /* This is fine (assuming malloc doesn't return NULL) */ 
}
```

# Dangling Pointer
A pointer pointing to a freed memory location are the location whose content has been deleted as called a dangling pointer.

- Dangling Pointer arise during object destruction when an object that has an incomming referencing is deleted or deallocated,without mdifying the value of the memory location of the deallocated memory.
See this image for better understanding
![](https://assets.dcoder.tech/5e2bb18339cc2918d4c0441a/610233f839e69755c7b1490e/storageemulated0dcimscreenshotsimg_20210729_170137.jpg)source :- java t point

Causes Of dangling pointer :-
1. deallocation of memory.
2. returning local variable in function calls.
3. variable going out of scope.


code
```c
#include <stdio.h>  
    int *fun(){  
    int y=10;  
    return &y;  
  }  
int main()  
{  
    int *p=fun();  
    printf("%d", *p);  
    return 0;  
}  
```
output will be
```
Segmentation fault
```
# Recommended to read also
hope you understand it have a good day,see you next time...

Disclaimer:- After this D.M.A(dynamic memory allocation) in c  is comming stay tuned,and follow.
anyone want to collaborate then comment me.

User also read these articles :-
  1.[A.I(artificial intelligence)](https://code.dcoder.tech/files/article/603f3cb440d0ea1344df99ad/a)
  
 2.[Loops in c](https://code.dcoder.tech/files/article/601bc82d62cf8b452bc67800/loops-in-c)
 
3.[Dcoder tutorial for bigginers👍👍](https://code.dcoder.tech/files/article/60a8b24c8a73600d5b6c2656/dcoder-tutorial-for-bigginers)

4.[About Python](https://code.dcoder.tech/files/article/6090bdf76b15f76d5162bae7/about-python)

5.[Operators in c](https://code.dcoder.tech/files/article/604f836ef00ce40617e53bbb/operators-in-c)

6.[Programmer vs coder](https://code.dcoder.tech/files/article/60e51fb2789de8069d392aa6/programmer-vs-coder)

## Author

- [@Sant yadav](https://github.com/sant608)
- source:- all from me some code and a photo has been taken from net(for better understanding).
- for any kind of mistakes forgive me and comment me that this is wrong it will appriciated a lot.
> a humble request to you please follow and give it a star.
and please don't forgot to comment about this i am waiting..

