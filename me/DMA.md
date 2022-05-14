Hello everyone,
let's get started to learn d.m.a in c🤘

There are two memory layouts in c:-
 > 1. Static memory allocation.
 > 2. Dynamic memory allocation.

definition of d.m.a:-
  ```
Dynamic memory is a way in which the size of a data structure can be changed during the runtime.
```
means it is a way to allocate and free memory at runtime during runtime.

**Difference between static and dynamic memory allocation**

| Static m.a |Dynamic m.a  |
| ---   | ---    |
| 1. allocation is done before the program's execution.      |1. allocation is done during the programs execution.         |
|2. there is no memory reusability and the memory allocated cannot be freed.       | 2. there is memory reusability and the allocated memory can be freed when not required.       |
|3. less efficient.       |3. more efficient. 


# Memory allocation in c
memory assigned to a program in a typical architecture can be broken down into four segments 

1. Code/text segment.
2. Static/global variables.
3. Stack.
4. Heap

- code segment is the place where code saves.
static variables like int a=5;

ex:-

  ```c
#include<stdio.h>
int main()
{
  int a=10;
  float b=20.5;
 //here int and float are bss segment
printf ("hello\n");
}
```
Static/global variables are of two types:-

There are two segments:-

1. data segment (initialised segment).

like 

2. Bss segment (uninitialised segment).

- As the program grows, so will the heap grow.

### Let's know about What is `Stack overflow`
- Compiler allocates some space for the stack part of the Memory.
- When this space gets exhausted(for some bad reason),the situation is called the stack overflow.

- typical example includes recursion with wrong base condition.

> So it is necessary to use `heap` carefully
### Let's Know about USe of `heap`
- There are lot of limitation of stack(S.M.A).
- Heap can be used flexibility by the programmer as per its needs.
- We can create a pointer in our main function and point to a memory block in the heap.
- The adress is stored by the local variable in the main function.
**Note**:-
> The memory consumption will not get freed automatically in case we overwrite the pointer.

So to control different types of actions C language gives us power to control memory allocation.

**Be carefully:**
As the more power comes to us,great responsibilty also come. 

There are major 4 functionsto handle operation with memory:-

1. calloc()
2. malloc()
3. realloc()
4. free()

# calloc()
syntax:-
```c
ptr = (cast-type*) malloc(size-in-bytes); //ptr is a pointer variable
```
1. calloc() stands for `contiguous allocation`.
2. It reserves `n` blocks of memory with the given amount of bytes.
3. The return value is a void pointer to the allocated space.
4. Therefore the void pointer need to typecasted to the appropriate type as per the requirement.
5. However,if the space is insufficiant,allocation of memory fails and it returns a `NULL` pointer.
6. All the value at allocated memory are initialized to 0.

example code:-
```c
#include <stdio.h>
#include <stdlib.h>
 
int main()
{
 
    // This pointer will hold the
    // base address of the block created
    int* ptr;
    int n, i;
 
    // Get the number of elements for the array
    n = 5;
    printf("Enter number of elements: %d\n", n);
 
    // Dynamically allocate memory using calloc()
    ptr = (int*)calloc(n, sizeof(int));
 
    // Check if the memory has been successfully
    // allocated by calloc or not
    if (ptr == NULL) {
        printf("Memory not allocated.\n");
        exit(0);
    }
    else {
 
        // Memory has been successfully allocated
        printf("Memory successfully allocated using calloc.\n");
 
        // Get the elements of the array
        for (i = 0; i < n; ++i) {
            ptr[i] = i + 1;
        }
 
        // Print the elements of the array
        printf("The elements of the array are: ");
        for (i = 0; i < n; ++i) {
            printf("%d, ", ptr[i]);
        }
    }
 
    return 0;
}
```
output:-
```
Enter number of elements: 5
Memory successfully allocated using calloc.
The elements of the array are: 1, 2, 3, 4, 5,
```


# malloc()
syntax:- 
```c
ptr=(ptr-type*) malloc(size-in-bytes);
```

1. Stands for `memory allocation`.
2. It reserves a block of memory with the given amount of bytes.
3. The return value is a void pointer needs to be typecasted to the appropriate type as per the requirement.
4. However,if the space is insufficiant,allocation of memory fails and it returns a `NULL` pointer.
5. All the value at allocated memory are initialized to garbage value(any random value).

example code:-
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{

  // This pointer will hold the
  // base address of the block created
  int* ptr;
  int n, i;

  // Get the number of elements for the array
  printf("Enter number of elements:");
  scanf("%d",&n);
  printf("Entered number of elements: %d\n", n);

  // Dynamically allocate memory using malloc()
  ptr = (int*)malloc(n * sizeof(int));

  // Check if the memory has been successfully
  // allocated by malloc or not
  if (ptr == NULL) {
    printf("Memory not allocated.\n");
    exit(0);
  }
  else {

    // Memory has been successfully allocated
    printf("Memory successfully allocated using malloc.\n");

    // Get the elements of the array
    for (i = 0; i < n; ++i) {
      ptr[i] = i + 1;
    }

    // Print the elements of the array
    printf("The elements of the array are: ");
    for (i = 0; i < n; ++i) {
      printf("%d, ", ptr[i]);
    }
  }

  return 0;
}

```
output:-
```
Enter number of elements: 5
Memory successfully allocated using malloc.
The elements of the array are: 1, 2, 3, 4, 5,
```
# realloc()
1. realloc stands for `reallocation`.
2. If the dynamically allocated memory is insufficiant we can change the size of priviously allocated memory using `realloc()` function.

syntax:-
```c
ptr=(ptr-type*) relloc(pointer name, new-size-in-bytes); // ptr is a pointer
```


example code:-
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{

  // This pointer will hold the
  // base address of the block created
  int* ptr;
  int n, i;

  // Get the number of elements for the array
  n = 5;
  printf("Enter number of elements: %d\n", n);

  // Dynamically allocate memory using calloc()
  ptr = (int*)calloc(n, sizeof(int));

  // Check if the memory has been successfully
  // allocated by malloc or not
  if (ptr == NULL) {
    printf("Memory not allocated.\n");
    exit(0);
  }
  else {

    // Memory has been successfully allocated
    printf("Memory successfully allocated using calloc.\n");

    // Get the elements of the array
    for (i = 0; i < n; ++i) {
      ptr[i] = i + 1;
    }

    // Print the elements of the array
    printf("The elements of the array are: ");
    for (i = 0; i < n; ++i) {
      printf("%d, ", ptr[i]);
    }

    // Get the new size for the array
    n = 10;
    printf("\n\nEnter the new size of the array: %d\n", n);

    // Dynamically re-allocate memory using realloc()
    ptr = realloc(ptr, n * sizeof(int));

    // Memory has been successfully allocated
    printf("Memory successfully re-allocated using realloc.\n");

    // Get the new elements of the array
    for (i = 5; i < n; ++i) {
      ptr[i] = i + 1;
    }

    // Print the elements of the array
    printf("The elements of the array are: ");
    for (i = 0; i < n; ++i) {
      printf("%d, ", ptr[i]);
    }

    free(ptr);
  }

  return 0;
}

```
output:-
```
try it you own.....
```

# free()

1. It is used to free the allocated memory.
2. If the dynamically allocated memory is required anymore, we can free it using free function.
3. This will free it using free function.
4. This will free the memory being used by the program in help.

syntax:-
```c
free(ptr); // ptr is a name of pointer variable
```
code:-
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{

  // This pointer will hold the
  // base address of the block created
  int *ptr, *ptr1;
  int n, i;

  // Get the number of elements for the array
  n = 5;
  printf("Enter number of elements: %d\n", n);

  // Dynamically allocate memory using malloc()
  ptr = (int*)malloc(n * sizeof(int));

  // Dynamically allocate memory using calloc()
  ptr1 = (int*)calloc(n, sizeof(int));

  // Check if the memory has been successfully
  // allocated by malloc or not
  if (ptr == NULL || ptr1 == NULL) {
    printf("Memory not allocated.\n");
    exit(0);
  }
  else {

    // Memory has been successfully allocated
    printf("Memory successfully allocated using malloc.\n");

    // Free the memory
    free(ptr);
    printf("Malloc Memory successfully freed.\n");

    // Memory has been successfully allocated
    printf("\nMemory successfully allocated using calloc.\n");

    // Free the memory
    free(ptr1);
    printf("Calloc Memory successfully freed.\n");
  }

  return 0;
}

```
output:-
```
Enter number of elements: 5
Memory successfully allocated using malloc.
Malloc Memory successfully freed.

Memory successfully allocated using calloc.
Calloc Memory successfully freed.
```
# example for whole mix code
example code of all function:-

```c
#include  <stdio.h>
#include  <stdlib.h>
//Compiler version gcc  6.3.0
     // use of malloc
int main()
{
//       int n;    
//  printf("enter the size of the array you want to create\n");
//         scanf("%d",&n);
// 
//  int  *ptr;
//      ptr = (int*) malloc(3*sizeof(int));
//    for (int i=0;i<n;i++)
//    {
//        printf("enter the value of %d of this array\n",i);
//        scanf("%d",&ptr[i]);
//    }
//          for (int i=0;i< n;i++)
//    {
//        printf(" the value at %d of this array %d \n",i, ptr[i]);
//        
//    }
        // use of calloc

    int n;    
printf("enter the size of the array you want to create\n");
       scanf("%d",&n);

int  *ptr;
    ptr = (int*)calloc(n , sizeof(int));
for (int i=0;i<n;i++)
{
   printf("enter the value of %d of this array\n",i);       // this for loop can be commnt out if this is commented the it will take enter the value of %d of this array but it display alll value 0
   scanf("%d",&ptr[i]);
}
        for (int i=0;i< n;i++)
  {
      printf(" the value at %d of this array %d \n",i, ptr[i]);
      
  }//
//  use of realloc

 printf("enter the new size of array you want to create\n");
        scanf("%d",&n);
     ptr = (int*)realloc(ptr ,n*sizeof(int));

for (int i=0;i<n;i++)

 {
   printf("enter the value of %d of this array\n",i);
    scanf("%d",&ptr[i]);
}
         for (int i=0;i< n;i++)
   {
   printf(" the new value at %d of this array is %d \n",i, ptr[i]);
   }
 free(ptr);        
  
}
```

Thanks for reading this i hope you liked it,see you next time


## Author

- @santyadav
- any kind of mistakes fogive me and tell me in comment if you got this.
- don't forgot to follow for more further updates.
- some(only some) codes has been taken from internet,and others from mine.
- you may also like to read these articles....

1. [Pointers in c](https://code.dcoder.tech/files/article/601f915612c1790ce40606f7/pointers-in-c)   
  
2. [Pointer in c part 2](https://code.dcoder.tech/files/article/610233f839e69755c7b1490e/pointer-in-c-part-2)
 
3. [Loops in c](https://code.dcoder.tech/files/article/601bc82d62cf8b452bc67800/loops-in-c)  
 
4. [A.I(artificial intelligence)](https://code.dcoder.tech/files/article/603f3cb440d0ea1344df99ad/a)   
 
 
5. [About Python](https://code.dcoder.tech/files/article/6090bdf76b15f76d5162bae7/about-python)
 
6. [Dcoder tutorial for bigginers👍👍](https://code.dcoder.tech/files/article/60a8b24c8a73600d5b6c2656/dcoder-tutorial-for-bigginers)
 
7. [How to run multiple files when it is created in a folder](https://code.dcoder.tech/files/article/609e60703aa0d1064119f1da/how-to-run-multiple-files-when-it-is-created-in-a-folder)
 
8. [Operators in c](https://code.dcoder.tech/files/article/604f836ef00ce40617e53bbb/operators-in-c)
 
 
 
 
 
