---
layout: lab
toc: false
title: "Module 2: Delays"
short_title: Delays
icon: fa-solid fa-stopwatch
order: 2
---

## What are Delays?

Since the computer runs our instructions very fast, sometimes we want to instruct it to stop and wait before continuing to run the next instruction.

Delay statements allow us to stop the computer for a set amount of time. 

What does this code do?


<img src="{% link media/delay.png %}">

This code turns on LED1 as red and LED10 as blue.  Then, it waits for 1 second before turning off LED1.


## Functions
The function to cause a delay in your code is this:
```c
delay(<milliseconds>);
```

* For `<milliseconds>`, indicate how long you want the computer to stop here for.  
* Remember, there are 1000 milliseconds in a second, so if you wanted to stop for 2.5 seconds, you would write `delay(2500);` in your code.

## Examples
To make LED3 display bright red and then switch to bright green after half a second, then switch to bright blue after another half second, you can use this code:
```c
leds_set_color(3, 255, 0, 0);
delay(500);
leds_set_color(3, 0, 255, 0);
delay(500);
leds_set_color(3, 0, 0, 255);
```

To make LED15 display bright yellow and then slowly turn off, you can use this code:
```c
leds_set_color(15, 255, 255, 0);
delay(500);
leds_set_color(15, 204, 204, 0);
delay(500);
leds_set_color(15, 153, 153, 0);
delay(500);
leds_set_color(15, 102, 102, 0);
delay(500);
leds_set_color(15, 51, 51, 0);
delay(500);
leds_set_color(15, 0, 0, 0);
```

## Exploration

> 📝 **_NOTE:_** You will need to go to `main.cpp` and change the comments to call the correct activity function:
```c
// led_activity();
delay_activity();
```

1. Change some of your previous code and add `delay` statements.  How does the behavior change?

1. Can you make an LED blink slowly?  Quickly?  


## Challenges

**Challenge 1:** Turn on LED5 as red. Wait 2 seconds and then turn it off and immediately turn on LED6 as red. Wait 2 seconds and move the red light to LED7, then LED8 and then LED9. \
<img src="{% link media/delay_challenge_1.gif %}" width="400" hspace="5%" vspace="10px">

**Challenge 2:** Repeat the previous challenge, but change the code so that the red light moves faster as it goes.  Start with 2 seconds for the first move, and then for each move, use half as much delay as the last move.  How long is your final delay? \
<img src="{% link media/delay_challenge_2.gif %}" width="400" hspace="5%" vspace="10px">

**Challenge 3:** Make LED1 and LED2 blink for 5 seconds but at different rates.  LED1 should blink once per second and LED2 should blink once every 2 seconds. Pick any color you would like for the LEDs. \
<img src="{% link media/delay_challenge_3.gif %}" width="400" hspace="5%" vspace="10px">

