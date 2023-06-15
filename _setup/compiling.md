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

In the above example, the second `leds_set_color()` statement is missing a semicolon at the end.  Fortunately, the compiler detects this and provides a helpful error message. 
The red error message in compiler log states: "<span style="color:red">src/main.cpp:151:30: expected ';' before 'leds_set_color'</span>".  The <span style="color:red">src/main.cpp</span> indicates that the problem is in the *main.cpp* file, and the <span style="color:red">151:30</span> means that the problem is on line number 151, and the 30<sup>th</sup> character. Notice that there is a red squiggle in the code where the error is too.

Another common error you might run into is when you misspell a function or variable name.  Function names must be spelled perfectly to compile correctly. Code is also case-sensitive, so capitalization matters! The code below has two errors, although they are easy to miss. One `leds_set_color()` statement is missing an 's' and one has a capitalized 's' that should be lower-case. Can you spot them?

<p align="center">
<img src="{% link media/mistyped_function_error.png %}" width="900" vspace="20px"></p>


Just because your code compiles without error, doesn't mean that it does what you are expecting.  Compiling and uploading without error just means that your code contains valid instructions for the computer to execute.  The instructions may not actually do what you are try to accomplish.

## What If My Board Isn't Working
Sometimes your board might get stuck in a bad state, and either you won't be able to upload your code, or your code will upload but won't run.  

_Note: Before following the next steps to reset your board, make sure the problem isn't actually in your code! It's easy to think that the board isn't working when it's really a bug in your code that's causing it to get stuck.  A good thing to try is to turn an LED on or off at the start of your code to see if it works.  Also, double check `main.cpp` to make sure the correct function is being called._


If your board is stuck, you can reset it by following these steps:


1. Unplug the board from your computer.

1. Restart VS Code.

1. Press random buttons on your board for about 30-60 seconds.

1. Hold down the button labeled "BOOT1" while plugging the board back into the computer.

1. While still holding down "BOOT1" try uploading.

1. Repeat until the board successfully uploads.
