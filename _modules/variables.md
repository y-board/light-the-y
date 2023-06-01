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

<details markdown="block">
<summary markdown="span">About Variable Types
</summary>

Notice that I only have to tell the _compiler_ what type of variable myFavoriteNumber is when I first declare it. If I change the value later, I don't have to include the type; the _compiler_ will remember it automatically. `myFavoriteNumber` is an `int` type variable, which means that it can only be a whole number. If my favorite number was 3.14, this type wouldn't work! Some other common variable types include `double` (for decimal numbers), `bool` (for `true` or `false` values), and `char` (for single characters like the letter `'a'`).
</details>

## Examples

Let's add a few variables to our code. In your `variables_activity.cpp` file, in the `variables_exploration` function definition, add the following lines of code:

```c
int currentLed = 1;
int currentNote = NOTE_C4;
int duration = 1000;
```

<details markdown="block">
<summary markdown="span">More Details
</summary>

Hopefully it's obvious what our variables represent based on their names. Notice that we can set our variables equal to other variables! `currentNote` has the same value as `NOTE_C4`. If we add `speaker_play_note(currentNote, duration)` to our code, it's the same as adding `speaker_play_note(NOTE_C4, 1000)`. Middle C will be played for one second.
</details>

We've now made three variables. Let's use them to do something interesting. First, let's light up our current LED. Add the following to your code, and upload it to your board:

```c
leds_set_color(currentLed, 255, 0, 0);
currentLed++;
leds_set_color(currentLed, 255, 0, 0);
currentLed++;
leds_set_color(currentLed, 255, 0, 0);
currentLed++;
leds_set_color(currentLed, 255, 0, 0);
```

<details markdown="block">
<summary markdown="span">More Details
</summary>

As you probably guessed by the lights on your board turning on, adding `++` to our variable name (with a semicolon at the end) increments the number our variable represents by 1. This is exactly the same as if we had written `currentLed = currentLed + 1`. It's nice that we don't have to hard-code the LED numbers into our code to tell the _compiler_ that we want to light them up. It makes our code a little easier to read.
</details>

## Exploration

1. Divide `currentNote` by 2 using the following code snippet: `currentNote = currentNote / 2;` Play a sound again. How does our new sound compare to our old one?

1. See what happens if you multiply or divide `currentNote` by powers of 2 (2, 4, 8, 16) and use it to play a sound. For example, how does the sound compare to our old ones if we write `currentNote = currentNote * 8;`?
    <details markdown="block">
    <summary markdown="span">Hint
    </summary>
    
    When we divide and multiply the frequency of notes by powers of 2, we get "octaves". For Middle C, this means we get higher or lower C notes.
    </details>

1. Light up three additional LEDs in the same way we did above.

## Challenges

**Challenge 1:** Light up all the LEDs on the board using the pattern above, then turn them all off again.

<details markdown="block">
<summary markdown="span">Hint
</summary>

We can use `currentNote--;` to decrement our variable by 1. This is the same as writing `currentNote = currentNote - 1;`
</details>

**Challenge 2:** Use the `currentNote` and `duration` variables to play notes with random sound lengths and frequencies

<details markdown="block">
<summary markdown="span">Hint
</summary>

You can use any mathematical expression you like and set your variable equal to it. For example: `duration = ((8 * 7) / 3) * 10;` or `currentNote = 2 * 2 * 2 + 1034;`
</details>

IMPORTANT: For your `variables_challenge1` and `variables_challenge2` functions, you will need to redeclare your variables. Variables live inside functions. If we are in a new function, the variable doesn't exist any more. Can you think of any other variables you might want to make?