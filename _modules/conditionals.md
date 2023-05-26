---
layout: lab
toc: false
title: "Module 6: Conditionals with Buttons and Switches"
short_title: Buttons and Switches
icon: fa-solid fa-toggle-on
order: 6
---

## What are Conditionals?

In this module, we'll explore **conditionals** which are statements in a program that evaluate to `true` or `false`. You've already seen conditionals when we learned about the **loop condition** in the last module. We'll begin here by exploring the **if statement**, which looks like the following:

```c
if (buttons_get(1)) {
    leds_set_color(1, 255, 0, 0);
}
```

This block of code tells our board to turn on LED1 _if_ Button1 is pressed. The function `buttons_get()` can be used as a **conditional** because it returns a `true` or `false` value that indicates whether the button that was passed into it (in this case Button1) is pressed. Notice that in an **if statement** the **conditional** is placed in parenthesis and the commands to execute if it is true are placed in curly braces.


## Examples
If you copy the above code into your program, and then try to upload it to your board and press the button, LED1 won't turn on! The reason why is that the _if_ statement is run immediately when you upload your code and it is only run once. In order to get the board to _continuously check_ the state of Button1 and turn LED1 on if it is pressed, we need to wrap our `if` statement in a `while` loop:

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

Now let's talk about the `else if` block. If we want to turn LED1 red when only one button is pressed, yellow when two buttons are pressed, or green when all three buttons are pressed, we could use the following:

```c
while (true) {
    if (buttons_get(1) && buttons_get(2) && buttons_get(3)) {
        leds_set_color(1, 0, 255, 0);
    } else if (buttons_get(1) && buttons_get(2)) {
        leds_set_color(1, 255, 255, 0);
    } else if (buttons_get(2) && buttons_get(3)) {
        leds_set_color(1, 255, 255, 0);
    } else if (buttons_get(1) && buttons_get(3)) {
        leds_set_color(1, 255, 255, 0);
    } else if (buttons_get(1)) {
        leds_set_color(1, 255, 0, 0);
    } else if (buttons_get(2)) {
        leds_set_color(1, 255, 0, 0);
    } else if (buttons_get(3)) {
        leds_set_color(1, 255, 0, 0);
    } else {
        leds_set_color(1, 0, 0, 0);
    }
}
```

There are two important things to notice in this example:

1. We can "chain" as many `else if` blocks together as we want! This gives us a lot of freedom to make our code do anything we want it to.

1. We introduced the use of `&&` which is a "logical AND". Using `&&` we can link _two or more_ conditionals together and only execute the code inside the block if they are ALL `true`. For example, we can read `if (buttons_get(1) && buttons_get(2) && buttons_get(3)) {...` as "if button 1 is pressed AND button 2 is pressed AND button 3 is pressed..."

Let's try one final example using a switch instead of a button:

```c
while (true) {
    while (true) {
        if (switches_get(2)) {
            leds_set_color(1, 255, 0, 0);
            break;
        }
    }
    while (true) {
        if (!switches_get(2)) {
            leds_set_color(1, 0, 0, 0);
            break;
        }
    }
}
```

Woah! That looks a little scary! We have infinite loops inside of infinite loops, and if statements inside of them. However, this code does exactly the same thing as our first example with a `while` loop above. If Switch2 on our board is ON, LED1 will turn on. And if Switch2 is OFF, LED2 will turn off.

There are a few important things to notice in this example:

1. There is a `break` statement inside of each `if` block. This tells the board that if our conditional is `true`, we want it to "break" out of the current `while` loop and move on. Because each of our inner `while` loops uses this pattern, and is inside an outer `while` loop, the inner loops will switch off between each other.

1. We have placed a `!` at the front of our conditional in our second inner `while` loop.This is called a "bang" and it inverts our condition. The conditional `if (!switches_get(2))` could be read as "if switch 2 is NOT on". If switch 2 is NOT on, then the code inside this `if` block will run.

1. This demonstrates that there is almost always more than one way to write code that works. Be creative, and try to find a solution that is simple, clear, and fast.

## Exploration

1. Reuse your code from the last module to make a single light circle around the board, but _only if Switch1 is turned on_.

1. Make the light circle around in the opposite direction _if Switch2 is on_ but if both switches are on or off, do nothing.

## Challenges

1. Make your board play a C note if Button1 is pressed, D note if Button2 is pressed, and E note if Button3 is pressed.
    * Hint: You can use a `while` loop inside your `if` statements to play the note for as long as you are holding the button. Use the same condition for both your `if` statements and your nested `while` loop. Set the duration on `speaker_play_note` to something small like 20ms.

1. Invert the conditionals for our "red, yellow, green" light example above using `!` operators so that not pressing any buttons yields a green light, one button yields a yellow light, two buttons yields a red light, and three buttons turns the light off. Can you make it so it does this for all of the lights on the board at the same time? 