---
layout: page
toc: false
title: "Coding Intro"
indent: 0
number: 2
icon: fa-solid fa-code
---

## Statements

Computer programs are made by writing a sequence of commands for the computer to execute.  These commands are called <u>instructions</u> or <u>statements</u>.

<img src="{% link media/code.png %}">

The computer processing chip (called a *microcontroller*) executes these instructions in sequence.  It can execute instructions VERY fast (up to 240 million per second), so even if you write several instructions in a sequence, it will execute them so fast it will appear to you that they execute instantly and all at the same time.

<img src="{% link media/semicolons.png %}">

**Important:** See how each statement ends with a semicolon?  This is <u>required</u> to indicate the end of a statement.  DON'T FORGET TO ADD THESE OR YOUR CODE WON'T RUN!

## Comments
Sometimes we want to tell the computer to ignore certain statements.  We can do this by adding `//` in front of any lines of code we want to disable.  

For example in the code below, we comment out the second statement so that now only LED1 and LED17 turns on (and LED13 does not).  The editor helps you remember that this code is commented out by turning it green.

<img src="{% link media/comments1.png %}">

Comments are also used to add personal messages to your code.  This is done to help you remember what your code is supposed to do.  It also helps others who look at your code to understand it.  Here is an example:

<img src="{% link media/comments2.png %}">


The editor will automatically comment or uncomment code for you if you put your cursor on the light and press `Ctrl + /`

## Functions and Braces

Functions are reusable pieces of code that perform a specified task. Just like mathematical functions, they take zero or more inputs and provide a single output. There are a few good reasons to use lots of functions in your code: 

1. If you find that certain parts of your code are repetitive, you can group the redundant code into its own function and reuse that function instead of typing everything out by hand every time. A good rule of thumb is that if you reuse it more than once, you should make it into a function.

1. Functions help make it more clear what you are doing, if you use good *naming conventions*:
    - Function names should be verbs (that is, they should be named after actions, not things... for example `runTests` or `turnOnLight` are good function names but `ledBrightness` or `kevin` are not)
    - Function names use camelCase, where the first letter is lowercase, all the words are put together (no spaces), and every newWordIsACapitalLetter

There are several parts of a function **declaration**:

1. The **function signature** which itself has a couple of parts:

    - The function **return type**. This can be void (no return type), int (a whole number), double (a decimal number), char (a single alphabetical character), or many others
    - The function **name** in camelCase
    - The function **parameters**, all enclosed in parenthesis, each with a type and a name \
<img src="{% link media/method_signatures.png %}">

1. The function body, enclosed in `{curly braces}`

    - Each statement in a function should end in a semi-colon and be on it's own line
    - The function should end with a `return` statement, that includes the variable to return (if the function has a void return type, then no variable should be returned) \
<img src="{% link media/function_body.png %}">

This is what complete function declarations look like. Notice one with a `void` return type (no return statement) and one with an `int` return type. Why can we return `int` instead of `double`? Will we ever return a decimal number? (Hint: look at the parameter types)

<img src="{% link media/two_functions.png %}">

Every program should have an `int main()` function. This function is special, because it is called automatically by the computer every time your program runs. It has an `int` return type, and typically returns 0 if the program runs successfully, or some other number if it runs into an undesired **error state**.

We can call functions inside of other functions! All we do is type the function name, provide any necessary parameters in parenthesis (or parenthesis with nothing between them if there are no parameters) and a semi-colon. We can also assign the value a function returns to variables:

<img src="{% link media/main_function_with_calls.png %}">

