---
layout: lab
toc: false
title: "Module 6: Conditionals with Buttons and Switches"
short_title: Buttons and Switches
icon: fa-solid fa-toggle-on
order: 6
---

## Functions

There are a two new functions we will use in this module. The first is the `buttons_get(<number>)` function. It returns a `true` value if the button we specify is pressed on our board and `false` if it is not pressed. For example, the variable button1IsPressed below has a `true` value if button 1 is pressed and `false` otherwise:

```c
bool button1IsPressed = buttons_get(1);
```

The second function to know is `switches_get(<number>)` which does the same thing as `buttons_get()` except for with the switches instead of the buttons.

## What are Conditionals?

In this module, we'll explore **conditionals** which are statements in a program that evaluate to `true` or `false`. You've already seen conditionals when we learned about the **loop condition** in the last module. We'll begin here by exploring the **if statement**, which looks like the following:

```c
if (buttons_get(1)) {
    leds_set_color(1, 255, 0, 0);
}
```

This block of code tells our board to turn on LED1 _if_ Button1 is pressed. The function `buttons_get()` can be used as a **conditional** because it returns a `true` or `false` value.

Notice that in an **if statement** the **conditional** is placed in parenthesis and the commands to execute if it is true are placed in curly braces.

Additionally, we can chain conditionals together using `&&` or `||`. The `&&` symbol is called a "logical AND", and the `||` symbol is called "logical OR". Here's an example of using each:

```c
if(buttons_get(1) && buttons_get(2)) {
    leds_set_color(1, 255, 0, 0);
}

if(switches_get(1) || switches_get(2)) {
    leds_set_color(1, 0, 0, 255);
}
```

The first `if` statement tells the board "if button 1 AND button 2 are pressed, turn led 1 red". The second `if` statement tells the board "if switch 1 OR switch 2 is on, turn led 1 blue".

Finally, we can compare numbers or values using `==`. For example, `if (1 == 3)...` will always be `false` and `if (1 < 3)...` will always be `true`. On the other hand, `if (buttons_get(1) == true)...` will be `true` if button 1 is pressed and `false` if it is not. Because `buttons_get(1)` already tells us this without comparing it, the `== true` part in this condition is not necessary. 


## Examples
If you copy one of the above examples into your program, and then try to upload it to your board and press the buttons, LED1 won't turn on! The reason why is that the _if_ statement is run immediately when you upload your code and it is only run once. In order to get the board to _continuously check_ the state of Button1 and turn LED1 on if it is pressed, we need to wrap our `if` statement in a `while` loop:

```c
while(true) {
    if (buttons_get(1)) {
        leds_set_color(1, 255, 0, 0);
    } else {
        leds_set_color(1, 0, 0, 0);
    }
}
```

Notice that we've added an `else` block to our `if` statement. This makes it so that if we let go of Button1, LED1 will turn off again.

Combining this with the skills you've learned with variables and `for` or `while` loops begins to introduce all kinds of fun possibilities for you to explore. For example, we could get the board to only check the state of our button for the first 10 seconds after we program it, and then light up LED15 after those 10 seconds, like this:

```c
for(int count = 0; count < 100; count++) {
    if (buttons_get(1)) {
        leds_set_color(1, 255, 0, 0);
    } else {
        leds_set_color(1, 255, 0, 0);
    }
    delay(100);
}
leds_set_color(15, 255, 0, 0);
```

This code block only checks if Button1 is pressed in 0.1 second increments for 10 seconds. 0.1 seconds is faster than the average person can press the button, so it will work just fine, and once the `for` loop is done, you can continue writing your code as normal.

Now let's talk about the `else if` block. If we want to turn LED1 red, yellow, or green depending on which _two_ buttons we press, we could use the following:

```c
while (true) {
    if (buttons_get(1) && buttons_get(2)) {
        leds_set_color(1, 255, 0, 0);
    } else if (buttons_get(2) && buttons_get(3)) {
        leds_set_color(1, 255, 255, 0);
    } else if (buttons_get(1) && buttons_get(3)) {
        leds_set_color(1, 0, 255, 0);
    } else {
        leds_set_color(1, 0, 0, 0);
    }
}
```

Notice that we can "chain" as many `else if` blocks together as we want! This gives us a lot of freedom to make our code do anything we want it to.

Let's try one final example using a switch instead of a button:

```c
while (true) {
    if(switches_get(2)) {
        while(switches_get(2)) {
            leds_set_color(1, 255, 0, 0);
        }
    } else {
        while(switches_get(2) == false) {
            leds_set_color(1, 0, 0, 0);
        }
    }
}
```

Woah! That looks a little scary! We have `if` statements inside of infinite loops, and more `while` loops inside of them. However, this code does exactly the same thing as our first example with a `while` loop above. If Switch2 on our board is ON, LED1 will turn on. And if Switch2 is OFF, LED2 will turn off.

There are a few important things to notice in this example:

1. The second conditional checks if Switch2 is NOT on using `switches_get(2) == false`

1. There is almost always more than one way to write code that works. Be creative, and try to find a solution that is simple, clear, and fast.

## Exploration

1. Reuse your code from the last module to make a single light circle around the board, but _only if Switch1 is turned on_.

1. Make the light circle around in the opposite direction _if Switch2 is on_ but if both switches are on or off, do nothing.

## Challenges

1. Make your board play a C note if Button1 is pressed, D note if Button2 is pressed, and E note if Button3 is pressed.
    * Hint: You can use a `while` loop inside your `if` statements to play the note for as long as you are holding the button. Use the same condition for both your `if` statements and your nested `while` loop. Set the duration on `speaker_play_note` to something small like 20ms.

1.  Use `&&` and `||` to chain conditions together so that if any one button is pressed LED1 turns red, if any two are pressed, LED1 turns yellow, and if all three are pressed LED1 turns green. Can you make all of the lights do this instead of just LED1?
    * Hint: use a `for` loop inside of your `if` statements