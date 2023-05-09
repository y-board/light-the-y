---
layout: page
toc: false
title: "Running Code"
indent: 0
number: 2
icon: fa-solid fa-person-running
---


In order to check that your code doesn't have any mistakes that will prevent it from running, it has to be checked by a special program called a *compiler*. The compiler takes the code you wrote and transforms it into instructions that the computer chip can understand.


## Uploading
In order to compile your code and upload it to the board, click the *right arrow* button at the bottom of the screen or select "Upload" from the dropdown in VS Code.
<p align="center"> <img src="{% link media/compiling_code.png %}" width="900" vspace="20px"></p>


If your code compiles correctly and uploads to the board, you should see something like this.  Note the green <span style="color:green">**SUCCESS**</span> text.

<p align="center"><img src="{% link media/successful_upload.png %}" width="900" vspace="20px"></p>



## Compile Errors

Compiling and uploading can fail for many reasons. For example:

<p align="center">
<img src="{% link media/semicolon_error.png %}" width="900" vspace="20px"></p>

In the above example, I forgot the semi-colon after my 2<sup>nd</sup> call to the `leds_set_color()` function. Luckily, the compiler is smart. The error message it provides will tell you what the problem is (`expected ';' before the next statement`) and where the problem is: `src/main.cpp:151:30` tells us that the problem is in the *main.cpp* file, line 151, the 30<sup>th</sup> character. Notice that there is a red squiggle in my code where the error is too.

Another common error you might run into is when you misspell a function or variable name. *COMPILERS ARE CASE SENSITIVE!!!* Even if you just have a single character capitalized incorrectly, it will cause an error. Two of the calls to `leds_set_color()` have mistakes. One is missing an 's' and one has a capitalized 's' that should be lower-case. Can you spot them?

<p align="center">
<img src="{% link media/mistyped_function_error.png %}" width="900" vspace="20px"></p>


Just because your code compiles without error, doesn't mean that it does what you are expecting.  Compiling and uploading without error just means that your code contains valid instructions for the computer to execute.  The instructions may not actually do what you are try to accomplish.
