---
layout: page
toc: false
title: "Running Your First Program"
short_title: "Running Code"
indent: 0
number: 2
icon: fa-solid fa-person-running
---

## Opening Files in Visual Studio Code

* Once you have Visual Studio Code running, click the file explorer icon in the top left (#1 in the image below).  This will open the file explorer on the left side of the screen.  From this you can view the files in your project.  
<p align="center"> <img src="{% link media/vscode_layout.png %}" width="900" vspace="20px"></p>
* Expand the `src` folder to see the files in your project. We will use a different file in this folder for each activity we do today.
* Double-click on the file named `main.cpp` to open it in the editor.  This program contains the `main()` function, which is the first function that runs when you upload your code to the board. 
* Look at the `main()` function (#2 in the image above).  You will see that right now it runs the function `test_program()`.  All of the other functions are commented out using `//` at the start of each line.  This means that they will not run when you upload your code to the board.  In later activities, you will come back to this file, comment out the `test_program()` function, and uncomment the activity function you want to run.  For now, leave it as is.




## Compiling and Uploading
In order to check that your code doesn't have any mistakes that will prevent it from running, it has to be checked by a special program called a *compiler*. The compiler takes the code you wrote and transforms it into instructions that the computer chip can understand.

You should now compile and upload the test program to your Y-Board:
* Click the *right arrow* button at the bottom of the screen or select "Upload" from the dropdown in VS Code.
<p align="center"> <img src="{% link media/compiling_code.png %}" width="900" vspace="20px"></p>


If your code compiles correctly and uploads to the board, you should see something like this.  Note the green <span style="color:green">**SUCCESS**</span> text.

<p align="center"><img src="{% link media/successful_upload.png %}" width="900" vspace="20px"></p>



## Compile Errors

Compiling and uploading can fail for many reasons. For example:

<p align="center">
<img src="{% link media/semicolon_error.png %}" width="900" vspace="20px"></p>

In the above example, the second `Yboard.set_led_color()` statement is missing a semicolon at the end.  Fortunately, the compiler detects this and provides a helpful error message. 
The red error message in compiler log states: "<span style="color:red">src/main.cpp:29:40: expected ';' before 'Yboard'</span>".  The <span style="color:red">src/main.cpp</span> indicates that the problem is in the *main.cpp* file, and the <span style="color:red">29:40</span> means that the problem is on line number 29, and the 40<sup>th</sup> character. Notice that there is a red squiggle in the code where the error is too.

Another common error you might run into is when you misspell a function or variable name.  Function names must be spelled perfectly to compile correctly. Code is also case-sensitive, so capitalization matters! The code below has an error, although it is easy to miss. One `Yboard.set_led_color()` statement has a capitalized 's' that should be lower-case. Can you spot the error?

<p align="center">
<img src="{% link media/mistyped_function_error.png %}" width="900" vspace="20px"></p>


Just because your code compiles without error, doesn't mean that it does what you are expecting.  Compiling and uploading without error just means that your code contains valid instructions for the computer to execute.  The instructions may not actually do what you are try to accomplish.

## What If My Board Isn't Working
Sometimes your board might get stuck in a bad state, and either you won't be able to upload your code.  If your board is stuck, you can reset it by following these steps:

1. Turn off the **PWR** switch.

1. While holding down the button labeled **BOOT**, turn on the **PWR** switch.

1. Let go of the **BOOT** button.

1. Try uploading your code again.
