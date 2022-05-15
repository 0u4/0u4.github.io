# C# Basic Tutorials: Variables

Variables, once you learn them, you'll always use them.
Variables are needed for practically everything, ranging from calculators, to games and a LOT more.
But, what are variables in C# and what do they do?



### 1: What they basically are:
Variables are, to put it simply, containers that hold information


### 2: Why to use them:
Now that you know what they are, why should you use them?
Let's say that, you're writing a story, but you want to change
the names of the characters. Instead of going into the code and
changing all of the names one by one, you can assign a single variable to
where those names used to be. So, instead of changing everything one by one,
you can just change one single variable, then all of the places where that
variable was in, changes aswell!


### 3: How to use them:
  
Now the part you've been waiting for, how to use them.

Let's go back to the example I previously told you.

You want a story, but you want to change the names of the characters easily, with a variable.

First, you must initialize the variable.
In C#, a variable can only have 1 type once initialized.
So, since you want a variable that holds text, the type should be a `string`.
To initialize it, simply put the scope (we'll talk about that in a later tutorial),
the data type, and the name all together. And of course the info.
So, here it is:
  
`string characterName = "Bob"; `
You might think, "I don't understand this".
I'll break it down.
`string` is the type of information the variable is holding. String, means a piece of text.
`characterName`  is just the name of the variable.
`=` just tells that the following text is what the variable is holding.
`"Bob";` is the information the variable holds. In this case, the information is "Bob".


Now, to use it.

Say you have this program, telling you a short story about Josh.
```
Console.WriteLine("Josh went to the store.");
Console.WriteLine("Josh bought some milk.");
Console.WriteLine("Josh went home.");
```
You want to change Josh to Bob, but you don't want to go in and change it one by one.

First, initialize the variable.

```
string characterName = "Bob";

Console.WriteLine("Josh went to the store.");
Console.WriteLine("Josh bought some milk.");
Console.WriteLine("Josh went home.");
```
Second, change all the "Josh" parts to characterName by
concatenating with the text like this.

```
string characterName = "Bob";
Console.WriteLine(characterName + " went to the store.");
Console.WriteLine(characterName + " bought some milk.");
Console.WriteLine(characterName + " went home.");
```
The + is just combining the text and the variable together.

You can also do it like this:
  
```
string characterName = "Bob";
Console.WriteLine($"{characterName} went to the store.");
Console.WriteLine($"{characterName} bought some milk.");
Console.WriteLine($"{characterName} went home.");
```
If you're doing it this way, make sure to not forget the dollar sign $ before
starting the actual text.

Now, you're done!
The output of this code will be:
```
Bob went to the store.
Bob bought some milk.
Bob went home.
```
To change the name, simply change the characterName variable!

### **Remarks:**
  
Variables can be used for SO MUCH MORE than just this.
I encourage you to learn more about variables and data types.

Data types:

- `string` - Holds text.
- `int` - Holds numbers.
- `bool` - Holds either **true** or **false**
- `double` - Holds numbers with a decimal point.



### Conclusion:
  
Now knowing this, hopefully you'll make some cool projects with this knowledge!

I hope you learned something today!

> Happy Coding!



Source:
[Signedint32](https://code.dcoder.tech/feed/article/5fe91e6114963b7675cf471b/c-tutorial-variables)
