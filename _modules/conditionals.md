---
layout: lab
toc: false
title: "Module 6: Conditionals with Buttons and Switches"
short_title: Buttons and Switches
icon: fa-solid fa-toggle-on
order: 6
---

<p markdown="1">
  <a data-toggle="collapse" href="#collapseExample" role="button" aria-expanded="false" aria-controls="collapseExample">
    + Buttons and Switches on the Y-Badge
  </a>
</p>
<div class="collapse" id="collapseExample">
  <div class="card card-body">
    There are 3 buttons and 2 switches we can use to control lights and sound on the Y-Badge board. There is also a switch for powering the board from the battery, and two buttons used to configure the board. All of them are labeled.
  </div>
</div>

<p align="center"><img src="{% link media/buttons_and_switches.png %}" width="400" hspace="5%" vspace="2%"></p>

## Functions

The function to determine if a button is pressed is:

```c
buttons_get(<button_number>);
```

And the function to determine if a switch is ON is:

```c
switches_get(<switch_number>);
```

<p markdown="1">
  <a data-toggle="collapse" href="#collapseConditionalFuncInfo" role="button" aria-expanded="false" aria-controls="collapseConditionalFuncInfo">
    + More Details
  </a>
</p>
<div class="collapse" id="collapseConditionalFuncInfo">
  <div class="card card-body">
    <p markdown="1">
        Each of these functions returns `true` if the button/switch is pressed or ON, and `false` otherwise. `<button_number>` or `<switch_number>` should be the number of the button or switch whose position you want to check as an `int` (eg. 1, 2, or 3).
    </p>
  </div>
</div>

## What are Conditionals?

We use **if statements** to evaluate **conditionals** that are `true` or `false`:

```c
if (buttons_get(1)) {
    leds_set_color(1, 255, 0, 0);
}
```

<p markdown="1">
  <a  data-toggle="collapse" href="#collapseIfExample" role="button" aria-expanded="false" aria-controls="collapseIfExample">
    + More Details
  </a>
</p>
<div class="collapse" id="collapseIfExample">
  <div class="card card-body">
    <p markdown="1">
        This block of code tells our board to turn on LED1 _if_ Button1 is pressed. The function `buttons_get()` can be used as a **conditional** because it returns a `true` or `false` value.
    </p>
    <p markdown="1">
        Notice that in an **if statement** the **conditional** is placed in parenthesis and the commands to execute if it is true are placed in curly braces.
    </p>
  </div>
</div>

Additionally, we can chain conditionals together using `&&` or `||`. The `&&` symbol is called a "logical AND", and the `||` symbol is called "logical OR". Here's an example of using each:

```c
if(buttons_get(1) && buttons_get(2)) {
    leds_set_color(1, 255, 0, 0);
}

if(switches_get(1) || switches_get(2)) {
    leds_set_color(1, 0, 0, 255);
}
```

<p markdown="1">
  <a data-toggle="collapse" href="#collapseLogicalOperators" role="button" aria-expanded="false" aria-controls="collapseLogicalOperators">
    + More Details
  </a>
</p>
<div class="collapse" id="collapseLogicalOperators">
  <div class="card card-body">
    <p markdown="1">
        The first `if` statement tells the board "if button 1 AND button 2 are pressed, turn led 1 red". The second `if` statement tells the board "if switch 1 OR switch 2 is on, turn led 1 blue".
    </p>
    <p markdown="1">
        There are several other important logical operators. For example, we can compare numbers or values using `==`. For example, `if (1 == 3)...` will always be `false` and `if (1 < 3)...` will always be `true`. On the other hand, `if (buttons_get(1) == true)...` will be `true` if button 1 is pressed and `false` if it is not. Because `buttons_get(1)` already tells us this without comparing it, the `== true` part in this condition is not necessary.
    </p>
    <p markdown="1">
        If you want to learn about the other logical operators, google "cpp logical operators".
    </p>
  </div>
</div>

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

<p markdown="1">
  <a data-toggle="collapse" href="#collapseInfLoopInfo" role="button" aria-expanded="false" aria-controls="collapseInfLoopInfo">
    + Why The Infinite Loop?
  </a>
</p>
<div class="collapse" id="collapseInfLoopInfo">
  <div class="card card-body">
    <p markdown="1">
        If you copy one of the above examples into your program, and then try to upload it to your board and press the buttons, LED1 won't turn on! The reason why is that the _if_ statement is run immediately when you upload your code and it is only run once. In order to get the board to _continuously check_ the state of Button1 and turn LED1 on if it is pressed, we need to wrap our `if` statement in a `while` loop:
    </p>
    <p markdown="1">
        Let's try combining more loops and if statements!
    </p>
  </div>
</div>

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

<p markdown="1">
  <a data-toggle="collapse" href="#collapseForIfInfo" role="button" aria-expanded="false" aria-controls="collapseForIfInfo">
    + More Details
  </a>
</p>
<div class="collapse" id="collapseForIfInfo">
  <div class="card card-body">
    <p markdown="1">
        This code block only checks if Button1 is pressed in 0.1 second increments for 10 seconds. 0.1 seconds is faster than the average person can press the button, so it will work just fine, and once the `for` loop is done, you can continue writing your code as normal.
    </p>
  </div>
</div>

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

<p markdown="1">
  <a data-toggle="collapse" href="#collapseElseIfInfo" role="button" aria-expanded="false" aria-controls="collapseElseIfInfo">
    + More Details
  </a>
</p>
<div class="collapse" id="collapseElseIfInfo">
  <div class="card card-body">
    <p markdown="1">
        Chaining conditionals gives us a lot of freedom to make our code do exactly what we want it to. The above example turns LED1 red, yellow, or green depending on which _two_ buttons we press.
    </p>
  </div>
</div>

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

<p markdown="1">
  <a data-toggle="collapse" href="#collapseNestedLoopInfo" role="button" aria-expanded="false" aria-controls="collapseNestedLoopInfo">
    + More Details
  </a>
</p>
<div class="collapse" id="collapseNestedLoopInfo">
  <div class="card card-body">
    <p markdown="1">
        Woah! That looks a little scary! We have `if` statements inside of infinite loops, and more `while` loops inside of them. However, this code does exactly the same thing as our first example with a `while` loop above. If Switch2 on our board is ON, LED1 will turn on. And if Switch2 is OFF, LED2 will turn off.
    </p>
    <p>
      There are a few important things to notice in this example:
      <ul>
        <li>
          The second conditional checkes if Switch2 is NOT on using <code>switches_get(2) == false</code>
        </li>
        <li>
          There is almost always more than one way to write code that works. Be creative, and try to find a solution that is simple, clear, and fast.
        </li>
      </ul>
    </p>
  </div>
</div>

## Exploration

1. Reuse your code from the last module to make a single light circle around the board, but _only if Switch1 is turned on_.

1. Make the light circle around in the opposite direction _if Switch2 is on_ but if both switches are on or off, do nothing.

## Challenges

**Challenge 1:** Make your board play a C note if Button1 is pressed, D note if Button2 is pressed, and E note if Button3 is pressed.

<p markdown="1">
  <a  data-toggle="collapse" href="#collapseConditionalsHint1" role="button" aria-expanded="false" aria-controls="collapseConditionalsHint1">
    + Hint
  </a>
</p>
<div class="collapse" id="collapseConditionalsHint1">
  <div class="card card-body">
    <p markdown="1">
        You can use a `while` loop inside your `if` statements to play the note for as long as you are holding the button. Use the same condition for both your `if` statements and your nested `while` loop. Set the duration on `speaker_play_note` to something small like 20ms.
    </p>
  </div>
</div>

**Challenge 2:** Use `&&` and `||` to chain conditions together so that if any one button is pressed LED1 turns red, if any two are pressed, LED1 turns yellow, and if all three are pressed LED1 turns green. Can you make all of the lights do this instead of just LED1?

<p markdown="1">
  <a  data-toggle="collapse" href="#collapseConditionalsHint2" role="button" aria-expanded="false" aria-controls="collapseConditionalsHint2">
    + Hint
  </a>
</p>
<div class="collapse" id="collapseConditionalsHint2">
  <div class="card card-body">
    <p markdown="1">
        Use a `for` loop inside of your `if` statements
    </p>
  </div>
</div>
