---
layout: lab
toc: false
title: "Module 5: Loops"
short_title: Loops
icon: fa-solid fa-arrow-rotate-left
order: 5
---

## What are Loops?

As a programmer, it's important to write code that isn't repetitive; it makes your program much easier to understand and speeds up the pace at which you can work. **Loops** are a fundamental programming tool we can use to eliminate repetitive code. Similar to functions, they can include as many commands inside them as you'd like. Unlike functions, they are able to _repeat those commands_ for as long as you want them to. We will explore two types of loops: **for loops** and **while loops**.

## For Loops

**For loops** are loops that run the code inside them _a specified number of times_. Here's an example:

```c
for (int currentLed = 1; currentLed <= 4; currentLed++) {
    leds_set_color(currentLed, 255, 0, 0);
}
```

This code does exactly the same thing as we did in the variables module: it turns the first four LEDs on your board red. But it takes only three lines of code (in the last module it took seven)! Even better, we can turn on as many _more_ LEDs as we'd like without changing our loop hardly at all. 

Let's break down how the for loop works.

* We use the keyword `for` to tell the _compiler_ we are creating a for loop.
* Inside the parenthesis, we have three commands:
    1. First, we declare a variable called `currentLed` and initialize it to 1. This variable is called the **loop variable** because it controls the loop.
    1. Second, we tell the board how long we want the _for loop_ to run for; that is, we want it to run until the `currentLed` is 4, then stop after turning on LED 4. This is called the **loop condition**.
    1. Third, we tell the board to increment the value of `currentLed` by 1 every time it runs the commands inside the for loop. This is called the **update statement**. Notice that there is no `;` after the **update statement**.
* Inside curly brackets, after the parenthesis, we have all of our commands to run as part of the loop.

Every time the for loop runs, the board will update the value of the **loop variable**, check the value, and determine if it still passes the **loop condition**. If it does, it will run the for loop again. If it doesn't, it will skip past the loop and continue executing any code that comes after it. What do you think you would have to change in the **loop condition** to turn on all the lights on your board?

One final piece of advice: we can make the **loop condition**, **loop variable**, and **update statement** anything we want. For example, the following code would turn the _last four_ LEDs red:

```c
for(int currentLed = 20; currentLed >= 16; currentLed--) {
    leds_set_color(currentLed, 255, 0, 0);
}
```
As you can see, we can make for loops run both _forward_ and _backward_!

## While Loops

**While loops** are loops that run the code inside them _until a certain condition is met_. This means that we can write for loops and while loops that do the same thing, but _for loops are better for running code a specific number of times and while loops are better for running code until a general condition is met in your program_. Here's an example of a while loop that does the same thing as the for loop above:

```c
currentLed = 1;
while (currentLed <= 4) {
    leds_set_color(currentLed, 255, 0, 0);
    currentLed++;
}
```

Notice that this is a little clunky. We have to declare currentLed _before_ the while loop, and put our **update statement** _inside_ the while loop. This means the code is a little longer, but we still use this pattern in programming quite often.

_While_ loops are extremely handy if we want something to repeat forever. For example, if I wanted to play C, D, E, and D in a loop forever, I could write the following:

```c
while (true) {
    speaker_play_note(NOTE_C4, 250);
    speaker_play_note(NOTE_D4, 250);
    speaker_play_note(NOTE_E4, 250);
    speaker_play_note(NOTE_D4, 250);
}
```

The **loop condition** here is always `true` so this is an **infinite loop**. It will run forever! While infinite loops can be very handy, they can also be tricky. In certain cases, you could crash your program if you don't realize you've created an infinite loop. For example, you couldn't increment a variable like currentLed forever in a while loop. Eventually the value would get so big that your program wouldn't be able to run anymore.


## Exploration:
1. Use a loop to turn on all the LEDs white. \
<img src="{% link media/white_lights.png %}" width="400" hspace="5%" vspace="10px">

1. Make all the LEDs blink. On for 500ms then off for 500ms, repeated forever.
    * Hint: Try using **for loops** _inside_ of a **while loop**.

    <img src="{% link media/white_blinking_lights.gif %}" width="400" hspace="5%" vspace="10px">

## Challenges:

1. Copy the code for "Twinkle Twinkle Little Star" from the `sound_activity.cpp` file and play it on repeat using a loop.

1. Make a single LED circle around the board, you choose the speed.

    <img src="{% link media/chasing_cw_lights.gif %}" width="400" hspace="5%" vspace="10px">

1. Change the last program to make the LED circle around the other direction.

    <img src="{% link media/chasing_ccw_lights.gif %}" width="400" hspace="5%" vspace="10px">