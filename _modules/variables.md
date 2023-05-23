---
layout: lab
toc: false
title: "Module 4: Variables"
short_title: Variables
icon: fa-solid fa-square-root-variable
order: 4
---

## What are Variables?

Variables are a way for us to store information in our program that we can change later. There are three parts to a variable: a **type**, a **name**, and a **value**. For example, I could store a variable in my program called "myFavoriteNumber" like this:

```c
int myFavoriteNumber = 8;
```

After I have _declared_ `myFavoriteNumber`, I can use it anywhere in my program. And if my favorite number changes later, I can change my variable to reflect that:

```c
myFavoriteNumber = 21;
```

Notice that I only have to tell the _compiler_ what type of variable myFavoriteNumber is when I first declare it. If I change the value later, I don't have to include the type; the _compiler_ will remember it automatically. `myFavoriteNumber` is an `int` type variable, which means that it can only be a whole number. If my favorite number was 3.14, this type wouldn't work! Some other common variable types include `double` (for decimal numbers), `bool` (for `true` or `false` values), and `char` (for single characters like the letter `'a'`).

## Examples

Let's add a few variables to our code. In your `variables_activity.cpp` file, in the `variables_exploration` function definition, add the following lines of code:

```c
int currentLed = 1;
int currentNote = NOTE_C4;
int delay = 1000;
```

We've now made three variables. Hopefully it's obvious what they represent based on their names. Notice that we can set our variables equal to other variables! `currentNote` has the same value as `NOTE_C4`. If we add `speaker_play_note(currentNote, delay)` to our code, it's the same as adding `speaker_play_note(NOTE_C4, 1000)`. Middle C will be played for one second.

Let's use our variables to do something interesting. First, let's light up our current LED. Add the following to your code, and upload it to your board:

```c
leds_set_color(currentLed, 255, 0, 0);
```

It's nice that we don't have to hard-code the number 1 into our code to tell the _compiler_ that we want to light it up. It makes our code a little easier to read. We can even use it to light up other leds. Add the following to your code and reupload it to your board:

```c
currentLed++;
leds_set_color(currentLed, 255, 0, 0);
currentLed++;
leds_set_color(currentLed, 255, 0, 0);
currentLed++;
leds_set_color(currentLed, 255, 0, 0);
```

As you probably guessed by the lights on your board turning on, adding `++` to our variable name (with a semicolon at the end) increments the number our variable represents by 1. We've now turned on the first four LEDs on without hard-coding their numbers anywhere!

## Exploration

1. Divide `currentNote` by 2 using the following code snippet: `currentNote = currentNote / 2;` Play a sound again. How does our new sound compare to our old one?

1. See what happens if you multiply or divide `currentNote` by powers of 2 and use it to play a sound. For example, how does the sound compare to our old ones if we write `currentNote = currentNote * 8;`?
    * Hint: when we divide and multiply the frequency of notes by powers of 2, we get "octaves". For Middle C, this means we get higher or lower C notes. 

1. Light up three additional LEDs in the same way we did above.

## Challenges

1. Light up all the LEDs on the board using the pattern above, then turn them all off again.
    * Hint: we can use `currentNote--;` to decrement our variable by 1.

1. Use the `currentNote` and `duration` variables to play notes with random sound lengths and frequencies
    * You can use any mathematical expression you like and set your variable equal to it. For example: `duration = ((8 * 7) / 3) * 10;` or `currentNote = 2 * 2 * 2 + 1034;`

* IMPORTANT: For your `variables_challenge1` and `variables_challenge2` functions, you will need to redeclare your variables. Variables live inside functions. If we are in a new function, the variable doesn't exist any more. Can you think of any other variables you might want to make?