# The C Language
C is one of the most widely used languages today and has served as the foundation for several other languages, such as C++, C#, Java, PHP, JavaScript, and many others. But how can we write a program in C?

Hello, World! And a Few More Things
We need to start writing our code, which will be our C program. To do this, we can use any text editor. We need to tell the computer that this is a C language file by using the .c extension.

Now that we have created the file, what do we put in it? What commands do we give the computer to start executing actions?

Let’s instruct C to print (printf) a message on the screen:

```c
printf("Hello, Alura!");
```

We have given our instruction to C. We told it to print a text. C requires that all text, also called a string, be enclosed in double quotes, and every instruction must end with a semicolon.

The code we wrote in C is readable for humans, meaning a person can read and understand it without much trouble. However, the computer does not understand this language.

We need to translate this language we wrote into a language that the computer can understand. This process of converting code from a programming language into machine code is called compilation.

When we compile a program, the compiler takes our code—written in C in this case—and converts it into a language the machine understands. There are several available compilers. Since I am using Linux, I will use GCC, which comes pre-installed in most distributions:

gcc hello-world.c
But wait… we couldn’t compile the code! GCC returned an error when we tried. Why did this happen?

We asked C to print a text on the screen, but where did we tell it where to find the printf instruction?

We need to tell C to use a function that handles data output, meaning a function that displays a message on the screen. To do this, we need to specify which library this function comes from.

In this case, the printf function comes from the standard input and output library, called stdio.h. To use it, we just need to include it in our file:

```c
#include <stdio.h>

printf("Hello, Alura!");
```

Great! Now if we try to compile our program, we’ll see the same error.

But we included the library that contains printf, so why does the error persist?

## The Main Function

### Every C program needs a main function (main) to run. This function indicates the entry point of the program. 

Since we want our printf to appear when the program runs, we need to declare it inside the main function. But how do we declare this function?

C has standardized the way we declare the main function. We simply write:
```c
int main() { … }
```
Everything inside the curly braces { } will be executed line by line when the program starts running:
```c
#include <stdio.h>

int main() {

    printf("Hello, Alura!");

}
```
Now, we can ask GCC or Clang to compile our file without getting an error!

## Running the Program

Nice, our file is compiled! Now, how do we run it?

Since we only asked GCC to compile the file, it automatically assigned a name to the compiled file. In my case, this name is a.out.

We can tell the computer to execute this file by typing ./ followed by the file name:

./a.out
Awesome! We successfully printed our message on the screen! Now, we can continue learning other functionalities of the language.

A Small Detail About Output Formatting
The percentage sign that appeared at the end of the phrase indicates that the string (the text we passed to printf) has ended. Since our instruction did not include a line break, the terminal inserted one automatically. However, this is not the standard behavior of the program.

By default, the line does not break. To ensure that our program always ends the message with a new line, we need to modify our printf statement to include \n:
```c
#include <stdio.h>

int main() {

    printf("Hello, Alura!\n");

}
```
When we compile and run the file again, we’ll see that the percentage sign disappears because the new line is now explicitly defined.

Customizing the Output File Name
In these examples, the compiler automatically assigns a name to our output file. But if we want, we can specify a name for the compiled file. To do this, we use the -o flag in GCC, followed by the desired output file name:

`gcc hello-world.c -o hello-world.out`

Understanding the int main() Return Value
One thing we need to pay attention to is the int keyword before the main function. This indicates the return type of the function. In other words, when we write int main(), we are saying that our function returns an integer number. But where do we specify this return value?

In some compilers, if we compile our code without a return value, we might get a warning saying that main does not return a value. This would not prevent the program from running, but it is not considered good practice.

By convention, the return value 0 indicates that the program executed successfully. So, we should explicitly tell main to return 0 at the end of execution:
```c
#include <stdio.h>

int main() {

    printf("Hello, Alura!\n");

    return 0;
}
```
## Conclusion
C is still one of the most widely used programming languages today. It has very high processing power and serves as the foundation for many modern programming languages.

At Alura, we offer three courses on C programming, each designed to help you learn the language through game development.

We also have a C programming course on Alura Start, where you can learn more about the language’s functionalities. Additionally, we provide courses that teach you how to use C to solve challenges from the Brazilian Informatics Olympiad, preparing you to create algorithms and compete at an advanced level.