---
layout: lab
toc: false
title: "Module 5: Loops"
short_title: Loops
icon: fa-solid fa-arrow-rotate-left
order: 5
---

<details markdown="block">
<summary markdown="span">What Are Loops?
</summary>

As a programmer, it's important to write code that isn't repetitive; it makes your program much easier to understand and speeds up the pace at which you can work. **Loops** are a fundamental programming tool we can use to eliminate repetitive code. Similar to functions, they can include as many commands inside them as you'd like. Unlike functions, they are able to _repeat those commands_ for as long as you want them to. We will explore two types of loops: **while loops** and **for loops**.
</details>

## While Loops

**While loops** are loops that run the code inside them _until a certain condition is met_. We can also use `while` loops to make our code run forever. For example, the following code will make LED1 on our board blink forever:

```c
while (true) {
    leds_set_color(1, 255, 0, 0);
    delay(250);
    leds_set_color(1, 0, 0, 0);
    delay(250);
}
```

<details markdown="block">
<summary markdown="span">More Details
</summary>

There are a few things to notice about this loop:

* The thing we place inside parenthesis after the `while` keyword is called the **loop condition**. The loop condition should be a statement that evaluates to either `true` or `false`. Because we've hard-coded `true` into this loop, the condition will never change and the loop will run forever.
* The commands we want the `while` loop to execute should be placed after the **loop condition** inside curly braces.
</details>

What if we wanted to use a `while` loop to make the first 10 leds blink one time each, in sequence? We could do something like the following:

```c
int currentLed = 1;
while(currentLed <= 10) {
    leds_set_color(currentLed, 255, 0, 0);
    delay(250);
    leds_set_color(currentLed, 0, 0, 0);
    currentLed++;
}
```

This loop has a **loop condition** that isn't always true, because we increment the value of `currentLed` every time it runs using `currentLed++;`. We want it to run as long as `currentLed <= 10` is true. Once `currentLed` is 11 or larger, the loop won't run again. 

## For Loops

A `for` loop to do the same thing as above looks like the following:

```c
for(int currentLed = 1; currentLed <= 10; currentLed++) {
    leds_set_color(currentLed, 255, 0, 0);
    delay(250);
    leds_set_color(currentLed, 0, 0, 0);
}
```

Seems like a better way of doing things, right?

<details markdown="block">
<summary markdown="span">More Details
</summary>

Our code to make the first 10 leds blink using a `while` loop is a little clunky. Did you notice that we had to declare a variable _outside of our loop_ called `currentLed` to keep track of our condition? And then we had to increment it _inside of our loop_. That's a little confusing.

`for` loops and `while` loops can do the same things, but _for loops are better for running code a certain number of times and while loops are better for running code until a certain condition is met in our program._

Notice the similarities between a `for` loop and a `while` loop. We still declare a variable called `currentLed`, we still have a **loop condition** that keeps track of whether the loop should run again, and we still increment `currentLed` every time the loop runs. But, we do all of that on a single line inside the parenthesis. This is a nice way to organize our code and keep track of our variable in one spot.
</details>

## Exploration:

> 📝 **_NOTE:_** You will need to go to `main.cpp` and change the comments to call the correct activity function:
```c
// variables_activity();
loop_activity();
```

1. Use a loop to turn on all the LEDs white. \
<img src="{% link media/white_lights.png %}" width="400" hspace="5%" vspace="10px">

1. Make all the LEDs blink. On for 500ms then off for 500ms, repeated forever.
    * Hint: Try using `for` loops _inside_ of a `while` loop.

    <img src="{% link media/white_blinking_lights.gif %}" width="400" hspace="5%" vspace="10px">

## Challenges:

_Remember to comment out the `loop_exploration();` call in the `loop_activity` function and uncomment the correct challenge function:_

```c
loop_exploration();
// loop_challenge1();
// loop_challenge2();
// loop_challenge3();
```

**Challenge 1:** Copy the code for "Twinkle Twinkle Little Star" from the `sound_activity.cpp` file and play it on repeat using a loop.

**Challenge 2:** Make a single LED circle around the board forever, you choose the speed. \
<img src="{% link media/chasing_cw_lights.gif %}" width="400" hspace="5%" vspace="10px">

**Challenge 3:** Change the last program to make the LED circle around the other direction. \
<img src="{% link media/chasing_ccw_lights.gif %}" width="400" hspace="5%" vspace="10px">