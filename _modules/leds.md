---
layout: lab
toc: false
title: "Module 1: LEDs"
short_title: LEDs
icon: fa-solid fa-lightbulb
order: 1
---


There are 20 LEDs on the Y-Board circuit board.

* Each LED is labeled LED1 to LED20.
* Each of these LEDs are RGB (red-green-blue) LEDs, meaning that they are actually three smaller red, green, and blue lights packaged together. For each LED, you can set the brightness of the red, green, and blue lights individually, making the LED appear to be any color you like.

<p align="middle">
<img src="{% link media/led_zoomed.png %}" width="32%" hspace="5%" vspace="2%">
<img src="{% link media/rgb_led.png %}" width="32%" hspace="5%" vspace="2%">
</p>

## Functions

To make things happen on the Y-Board, you will need to call **functions** from your code. A function is a set of instructions that a computer can follow to perform a specific task. Functions are very useful because they allow programmers to write code that can be reused multiple times in a program.

The function to set an LED color looks like this:
```cpp
Yboard.set_led_color(<LED number>, <red>, <green>, <blue>);
```

* The `<LED number>` can be any value from 1 to 20.
* The `red`, `green`, and `blue` values represent the brightness of that color and can be any value from 0 to 255.

## Examples
To make LED3 display bright red, you should use this statement in your code (don't forget to add the semicolon):

```cpp
Yboard.set_led_color(3, 255, 0, 0);
```

To make LED15 display bright yellow, you should turn on the red and green pixels to max brightness:
```cpp
Yboard.set_led_color(15, 255, 255, 0);
```

Add the example code to your own to test it out. Don't forget to click "upload" in the top right corner dropdown to program your board with new code! 
<p align="middle"><img src="{% link media/upload_examples.png %}" width="800" vspace="10px"></p>

## Exploration

1. Pick an LED of your choice and turn it on.

1. What happens if you use **_255, 255, 255_** for your RGB values? 

1. What happens if you use _**0, 0, 0**_ for your RGB values?

1. Figure out the RGB value for your favorite color by using the `Yboard.set_led_color`.


## Challenges

_Remember to comment out the `led_exploration();` call in the `led_activity` function and uncomment the correct challenge function:_

```c
// led_exploration();
led_challenge1();
// led_challenge2();
// led_challenge3();
```

**Challenge 1:** Turn on LEDs 1, 13, and 17. Make them 3 different colors.

<img src="{% link media/led_challenge_1.jpg %}" width="400" hspace="5%" vspace="10px">

**Challenge 2:** Make one of the LEDs orange.

<img src="{% link media/led_challenge_2.jpg %}" width="400" hspace="5%" vspace="10px">

**Challenge 3:** Turn on all of the LEDs with a progression between colors, starting with pure red and going to pure blue.

<img src="{% link media/led_challenge_3.jpg %}" width="400" hspace="5%" vspace="10px">

