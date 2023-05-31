---
layout: lab
toc: false
title: "Module 6: Conditionals with Buttons and Switches"
short_title: Buttons and Switches
icon: fa-solid fa-toggle-on
order: 6
---

<details markdown="block">
<summary markdown="span">Buttons and Switches on the Y-Badge
</summary>

There are 3 buttons and 2 switches we can use to control lights and sound on the Y-Badge board. There is also a switch for powering the board from the battery, and two buttons used to configure the board. All of them are labeled.
</details>

<p align="center"><img src="{% link media/buttons_and_switches.png %}" width="400" hspace="5%" vspace="2%"/></p>

## Functions

The function to determine if a button is pressed is:

```c
buttons_get(<button_number>);
```

And the function to determine if a switch is ON is:

```c
switches_get(<switch_number>);
```

<details markdown="block">
<summary markdown="span">More Details
</summary>

Each of these functions returns `true` if the button/switch is pressed or ON, and `false` otherwise. `<button_number>` or `<switch_number>` should be the number of the button or switch whose position you want to check as an `int` (eg. 1, 2, or 3).
</details>

## What are Conditionals?

We use **if statements** to evaluate **conditionals** that are `true` or `false`:

```c
if (buttons_get(1)) {
    leds_set_color(1, 255, 0, 0);
}
```

<details markdown="block">
<summary markdown="span">More Details
</summary>

This block of code tells our board to turn on LED1 _if_ Button1 is pressed. The function `buttons_get()` can be used as a **conditional** because it returns a `true` or `false` value.

Notice that in an **if statement** the **conditional** is placed in parenthesis and the commands to execute if it is true are placed in curly braces.
</details>

Additionally, we can chain conditionals together using `&&` or `||`. The `&&` symbol is called a "logical AND", and the `||` symbol is called "logical OR". Here's an example of using each:

```c
if(buttons_get(1) && buttons_get(2)) {
    leds_set_color(1, 255, 0, 0);
}

if(switches_get(1) || switches_get(2)) {
    leds_set_color(1, 0, 0, 255);
}
```

<details markdown="block">
<summary markdown="span">More Details
</summary>

The first `if` statement tells the board "if button 1 AND button 2 are pressed, turn led 1 red". The second `if` statement tells the board "if switch 1 OR switch 2 is on, turn led 1 blue".

There are several other important logical operators. For example, we can compare numbers or values using `==`. For example, `if (1 == 3)...` will always be `false` and `if (1 < 3)...` will always be `true`. On the other hand, `if (buttons_get(1) == true)...` will be `true` if button 1 is pressed and `false` if it is not. Because `buttons_get(1)` already tells us this without comparing it, the `== true` part in this condition is not necessary.

If you want to learn about the other logical operators, google "cpp logical operators".
</details>

## Examples
We can use an `else` block to make the board do something else when the `if` block is `false`:

```c
while(true) {
    if (buttons_get(1)) {
        leds_set_color(1, 255, 0, 0);
    } else {
        leds_set_color(1, 0, 0, 0);
    }
}
```

<details markdown="block">
<summary markdown="span">Why The Infinite Loop?
</summary>

If you copy one of the above examples into your program, and then try to upload it to your board and press the buttons, LED1 won't turn on! The reason why is that the _if_ statement is run immediately when you upload your code and it is only run once. In order to get the board to _continuously check_ the state of Button1 and turn LED1 on if it is pressed, we need to wrap our `if` statement in a `while` loop.

Let's try combining more loops and if statements!
</details>

We could get the board to only check the state of our button for the first 10 seconds after we program it, and then light up LED15 after those 10 seconds, like this:

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

<details markdown="block">
<summary markdown="span">More Details
</summary>

This code block only checks if Button1 is pressed in 0.1 second increments for 10 seconds. 0.1 seconds is faster than the average person can press the button, so it will work just fine, and once the `for` loop is done, you can continue writing your code as normal.
</details>

We can chain as many conditionals together as we want by using `else if` blocks:

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

<details markdown="block">
<summary markdown="span">More Details
</summary>

Chaining conditionals gives us a lot of freedom to make our code do exactly what we want it to. The above example turns LED1 red, yellow, or green depending on which _two_ buttons we press.
</details>

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

<details markdown="block">
<summary markdown="span">More Details
</summary>

Woah! That looks a little scary! We have `if` statements inside of infinite loops, and more `while` loops inside of them. However, this code does exactly the same thing as our first example with a `while` loop above. If Switch2 on our board is ON, LED1 will turn on. And if Switch2 is OFF, LED2 will turn off.

There are a few important things to notice in this example:

* The second conditional checks if Switch2 is NOT on using `switches_get(2) == false`
* There is almost always more than one way to write code that works. Be creative, and try to find a solution that is simple, clear, and fast.
</details>

## Exploration

1. Reuse your code from the last module to make a single light circle around the board, but _only if Switch1 is turned on_.

1. Make the light circle around in the opposite direction _if Switch2 is on_ but if both switches are on or off, do nothing.

## Challenges

**Challenge 1:** Make your board play a C note if Button1 is pressed, D note if Button2 is pressed, and E note if Button3 is pressed.

<details markdown="block">
<summary markdown="span">Hint
</summary>

You can use a `while` loop inside your `if` statements to play the note for as long as you are holding the button. Use the same condition for both your `if` statements and your nested `while` loop. Set the duration on `speaker_play_note` to something small like 20ms.
</details>

**Challenge 2:** Use `&&` and `||` to chain conditions together so that if any one button is pressed LED1 turns red, if any two are pressed, LED1 turns yellow, and if all three are pressed LED1 turns green. Can you make all of the lights do this instead of just LED1?

<details markdown="block">
<summary markdown="span">More Details
</summary>

Use a `for` loop inside of your `if` statements.
</details>