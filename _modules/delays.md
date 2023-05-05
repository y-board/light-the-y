---
layout: lab
toc: false
title: "Module 2: Delays"
short_title: Delays
number: 2
order: 2
---

## What are Delays?

Since the computer runs our instructions very fast, sometimes we want to instruct it to stop and wait before continuing to run the next instruction.

Delay statements allow us to stop the computer for a set amount of time. 

What does this code do?


<img src="{% link media/delay.png %}">

## Examples
* TODO: Add an example?


## Functions
The function to cause a delay in your code is this:
```c
delay(<milliseconds>);
```

* For \<milliseconds\>, indicate how long you want the computer to stop here for.  
* Remember, there are 1000 milliseconds in a second, so if you wanted to stop for 2.5 seconds, you would write `delay(2500);` in your code.

## Explore
1. Change some of your previous code and add `delay` statements.  How does the behavior change?

1. Can you make an LED blink slowly?  Quickly?  


## Challenges

1. Turn on LED5 as red. Wait 2 seconds and then turn it off and immediately turn on LED6 as red. Wait 2 seconds and move the red light to LED7, then LED8 and then LED9.

1. Repeat the previous challenge, but change the code so that the red light moves faster as it goes.  Start with 2 seconds for the first move, and then for each move, use half as much delay as the last move.  How long is your final delay?

<!-- TODO: Add GIF -->

