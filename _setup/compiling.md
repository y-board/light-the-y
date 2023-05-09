---
layout: page
toc: false
title: "Running Code"
indent: 0
number: 2
icon: fa-solid fa-person-running
---

## Uploading Code to Your Board

In order to check that your code doesn't have any mistakes that will prevent it from running, it has to be checked by a special program called a *compiler*. The compiler takes human-readable code and converts it into machine code (1's and 0's) that the computer can read and execute.

In order to compile your code and upload it to the board, click the *right arrow* button at the bottom of the screen or select "Upload" from the dropdown in VS Code.

<img src="{% link media/compiling_code.png %}">

After a few seconds, VS code will tell you if your code was successfully uploaded or if there was an error. Errors can occur for many reasons. For example:

<img src="{% link media/semicolon_error.png %}">

In the above example, I forgot the semi-colon after my call to the `ex7()` function. Luckily, the compiler is smart. The error message it provides will tell you what the problem is ('expected ';' before the next statement) and where the problem is. src/main.cpp:151:8 tells us that the problem is in the main.cpp file, line 151, the 8th character. Notice that there is a red squiggle in my code where the error is too.

Another common error you might run into is when you misspell a function or variable name. *COMPILERS ARE CASE SENSITIVE!!!* Even if you just have a single character capitalized incorrectly, it will cause an error:

<img src="{% link media/mistyped_function_error.png %}">

If your code is error free, it will upload to the board. This doesn't mean that your code will always do what you are expecting, just that you don't have any syntax errors or typos. Your instructions still will do exactly what you specify, so if there is a flaw in your *logic*, it could compile but still cause unexpected behavior. When your code has successfully compiled and uploaded to your board, it will look like this: 

<img src="{% link media/successful_upload.png %}">