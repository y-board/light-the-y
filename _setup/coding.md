---
layout: page
toc: false
title: "Coding Intro"
indent: 0
number: 2
icon: fa-solid fa-code
---

<details markdown="block">
<summary markdown="span">Project Layout Information
</summary>

The project code is organized in a way that makes it easy for you to write separate code for each module:

* You should begin _each activity_ in `src/main.cpp` which is the `main.cpp` file in the `src` folder of the project. `main.cpp` has several function calls with names like `led_activity();` or `loop_activity();` on lines 14-20. You should uncomment the function call for the activity you are currently working on by _removing_ the `//` from in front of it. Make sure the function calls on lines 14-20 for the activities you are _not_ currently working on _have_ the `//` in front of them.

* Each function call on lines 14-20 of `main.cpp` has a corresponding file. For example, `led_activity();` corresponds to a file named `led_activity.cpp` in the `src` folder of the project.

* You should navigate to the file that corresponds to your current activity and write all of your code for that activity in that file.

* For each activity and its corresponding file, there is an activity function that calls other functions for exploration and two or more challenges. These function calls should be commented or uncommented depending on which one you are working on _just like how only the current activity was uncommented in `main.cpp`._

* Write the code for the activity's exploration and challenge sections inside the curly braces for the corresponding function definitions.

* You may choose to add the code provided in the **Example** sections of each module to the exploration function, so that you can see how it works.

* For more information about functions, see the _Coding Intro_ page.

</details>

## Statements

Computer programs are made by writing a sequence of commands for the computer to execute.  These commands are called *instructions* or *statements*. In the example below, there are five statements that control the LEDs and buttons on the Y-Board.

```cpp
Yboard.set_led_color(1, 255, 0, 0); 
Yboard.set_led_color(13, 0, 255, 0);
Yboard.set_led_color(17, 0, 0, 255);

int b = Yboard.get_button(1);

Yboard.set_led_color(1, 255 * b, 0, 0);
```

The computer processing chip (called a *microcontroller*) executes these instructions in sequence.  It can execute instructions VERY fast (up to 240 million per second), so even if you write several instructions in a sequence, it will execute them so fast it will appear to you that they execute instantly and all at the same time.

```cpp
Yboard.set_led_color(1, 255, 0, 0); 
Yboard.set_led_color(13, 0, 255, 0);
Yboard.set_led_color(17, 0, 0, 255);
```

**Important:** See how each statement ends with a semicolon?  This is *required* to indicate the end of a statement.  DON'T FORGET TO ADD THESE OR YOUR CODE WON'T RUN!

## Comments
Sometimes we want to tell the computer to ignore certain statements.  We can do this by adding `//` in front of any lines of code we want to disable. This is called a **comment**. 

For example in the code below, we comment out the second statement so that now only LED1 and LED17 turns on (and LED13 does not).  The editor helps you remember that this code is commented out by turning it green.

```cpp
Yboard.set_led_color(1, 255, 0, 0); 
// Yboard.set_led_color(13, 0, 255, 0);
Yboard.set_led_color(17, 0, 0, 255);
```

Comments are also used to add personal messages to your code.  This is done to help you remember what your code is supposed to do.  It also helps others who look at your code to understand it.  Here is an example:

```cpp
// Turn on LED10 as green
Yboard.set_led_color(10, 0, 255, 0);

// Turn on LED15 as blue, but not as bright
Yboard.set_led_color(15, 0, 0, 100);
```

The editor will automatically comment or uncomment code for you if you put your cursor on the line and press `Ctrl + /`

## Functions and Braces
Sometimes it is helpful to group together code statements into blocks of code that you can run in one easy step.  Grouping the statements together is like creating a *recipe* of directions.  This is called a **function**.

The code below shows two different functions (`turnOnLEDs` and `turnOffLEDs`) that turn on or off the first three LEDs.  Functions start with an open brace `{` and end with a close brace `}`.  All of the instructions within the braces make up the recipe of the function.

<img src="{% link media/functions.png %}" hspace="5%" width="500">

You can run the function recipe by **calling** a function.  This is done by writing a statement with the function name followed by parenthesis `()`. In the above code, the statements at <span style="color:green">**1**</span> and <span style="color:green">**5**</span> run the `turnOnLEDs` function to turn on the three LEDs.  The statement at <span style="color:red">**3**</span> runs the `turnOffLEDs` function to turn off the three LEDs. 

Using functions helps us organize our code to make it easier to understand.  It also allows us to *reuse* code, by calling the same recipe of instructions multiple times.  


