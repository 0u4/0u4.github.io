## hii guys if you Don't know how to use if else statement in c then this is for you

> first we have understand the meaning of if and else.
### if means you are geaving a condition.
like if n=5;
then execute the line.
ok,now understand like this from your daily life.
if i have 90 rupees or  more then 90 rupees then only i will eat cake.

so here if i have 90 rupee or more then 90 rupees left then i am going to eat a cake else not.
syntax

```c
if(condition)
{
 /*code*/
}
else
{
  /*code*/
}
```
```c
#include<stdio.h>
int main()
{
  int rupees;
  printf("Enter the how many rupee you have left\n");
  scanf("%d",& rupees);
  if(rupees>=90)
  {
    printf("i am going to eat cake");
  }
  else
    printf("oh! i have not sufficient money to eat cake");

}
```
look at the code below.
```c
 int main()
  {
  int i=5;
   if(i==5)
   {
    printf("yes\n");
   }
    else
   {
    printf("no");
   }
 }
 ```
# you can check my file as an example
* [if else 6.c](https://code.dcoder.tech/files/code/5ed1c3a9925ae47ccd0a3bc5/if-else-6)
``` 
#include<stdio.h>
#include<conio.h>
main()
{
  int x,y,z;
  clrscr();
  printf("enter your firt semester total marks out of 100\n");
  scanf("%d",&x);
  printf("enter your second semester total marks out of 100\n");
  scanf("%d",&y);
  printf("sum of your first and second semester marks is:-%d\n",z=x+y);
  if(z<50)
  {
    
  printf("you are fail");
  }
  else
  {
  printf("you are pass");
  }
  getch();
  
}
```

so this is the simple if else statement
syntax
```c
if(condition )
{
  */code*/
}
# you simply use only if without else look this example
int main()
{
  int i=5;
  if(i=5)
  {
    printf("this is 5");
  }
}

```
so here you can see there is no else statement.

## you can use if else ladder like if there are more than two  conditions 
condition 1.i may be go to school today
condition 2.i can go delhi today 
condition 3.i can go to meet sister's house today
there can be many more possibility.
# in such cases you have option to use if else ladder

sytax of if else ladder
```c
if (condition)
    statement 1;
else if (condition)
    statement 2;
.
.
else
    statement;    
 ```   
# now look at the example 
    
 ```c
    
include <stdio.h> 

int main() 
{ 

    int i = 20; 

  

    // Check if i is 10 

    if (i == 10) 

        printf("i is 10"); 

  

    // Since i is not 10 

    // Check if i is 15 

    else if (i == 15) 

        printf("i is 15"); 

  

    // Since i is not 15 

    // Check if i is 20 

    else if (i == 20) 

        printf("i is 20"); 
        

    // If none of the above conditions is true 

    // Then execute the else statement 

    else

        printf("i is not present"); 

    return 0; 
} 
```    

 ```
 if you like it please follow me for more updates about c programming      
and don't forget to tell me in comment is this was helpful for you    
```

# thank you all have a nice day  👍
    
    
    
    
    
