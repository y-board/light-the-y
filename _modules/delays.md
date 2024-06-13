---
layout: lab
toc: false
title: "Module 2: Delays"
short_title: Delays
icon: fa-solid fa-stopwatch
order: 2
---

<details markdown="block">
<summary markdown="span">What Are Delays?
</summary>

Since the computer runs our instructions very fast, sometimes we want to instruct it to stop and wait before continuing to run the next instruction.

Delay statements allow us to stop the computer for a set amount of time.
</details>

```cpp
Yboard.set_led_color(1, 255, 0, 0);  // Run these together first
Yboard.set_led_color(10, 0, 0, 255); 
delay(1000);                         // Wait a bit
Yboard.set_led_color(1, 0, 0, 0);    // Then run this
```

This code turns on LED1 as red and LED10 as blue.  Then, it waits for 1 second before turning off LED1.

## Functions
The function to cause a delay in your code is this:
```c
delay(<milliseconds>);
```

<details markdown="block">
<summary markdown="span">Explanation
</summary>

* For `<milliseconds>`, indicate how long you want the computer to stop running more code for.
* Remember, there are 1000 milliseconds in a second, so if you wanted to stop for 2.5 seconds, you would write `delay(2500);` in your code.
</details>

## Examples
To make LED3 display bright red and then switch to bright green after half a second, then switch to bright blue after another half second, you can use this code:

```cpp
Yboard.set_led_color(3, 255, 0, 0);
delay(500);
Yboard.set_led_color(3, 0, 255, 0);
delay(500);
Yboard.set_led_color(3, 0, 0, 255);
```

To make LED15 display bright yellow and then slowly turn off, you can use this code:
```cpp
Yboard.set_led_color(15, 255, 255, 0);
delay(500);
Yboard.set_led_color(15, 204, 204, 0);
delay(500);
Yboard.set_led_color(15, 153, 153, 0);
delay(500);
Yboard.set_led_color(15, 102, 102, 0);
delay(500);
Yboard.set_led_color(15, 51, 51, 0);
delay(500);
Yboard.set_led_color(15, 0, 0, 0);
```

## Before You Start

Each time we start a new activity, you will need to go to the `main.cpp` file and change which activity function is called when the program starts up. Before proceeding, go to `main.cpp` and comment out the `led_activity()` function call, and uncomment the `delay_activity()` function call:
```c
// led_activity();
delay_activity();
```

## Exploration


1. Change some of your previous code and add `delay` statements.  How does the behavior change?

1. Can you make an LED blink slowly?  Quickly?  


## Challenges

_As you work on the challenges below, we don't want you to erase your existing code.  Instead, each challenge will be coded in their own function.  You will need to comment out the `delay_exploration();` call in the `delay_activity` function and uncomment the correct challenge function:_

```c
delay_exploration();
//   delay_challenge1();
//   delay_challenge2();
//   delay_challenge3();
```

**Challenge 1:** Turn on LED5 as red. Wait 2 seconds and then turn it off and immediately turn on LED6 as red. Wait 2 seconds and move the red light to LED7, then LED8 and then LED9. \
<img src="{% link media/delay_challenge_1.gif %}" width="400" hspace="5%" vspace="10px">

**Challenge 2:** Repeat the previous challenge, but change the code so that the red light moves faster as it goes.  Start with 2 seconds for the first move, and then for each move, use half as much delay as the last move.  How long is your final delay? \
<img src="{% link media/delay_challenge_2.gif %}" width="400" hspace="5%" vspace="10px">

**Challenge 3:** Make LED1 and LED2 blink for 5 seconds but at different rates.  LED1 should blink once per second and LED2 should blink once every 2 seconds. Pick any color you would like for the LEDs. \
<img src="{% link media/delay_challenge_3.gif %}" width="400" hspace="5%" vspace="10px">

