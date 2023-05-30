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

<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseVariableTypeInfo" role="button" aria-expanded="false" aria-controls="collapseVariableTypeInfo">
    About Variable Types
  </a>
</p>
<div class="collapse" id="collapseVariableTypeInfo">
  <div class="card card-body">
    <p>
        Notice that I only have to tell the <em>compiler</em> what type of variable myFavoriteNumber is when I first declare it. If I change the value later, I don't have to include the type; the <em>compiler</em> will remember it automatically. <code>myFavoriteNumber</code> is an <code>int</code> type variable, which means that it can only be a whole number. If my favorite number was 3.14, this type wouldn't work! Some other common variable types include <code>double</code> (for decimal numbers), <code>bool</code> (for <code>true</code> or <code>false</code> values), and <code>char</code> (for single characters like the letter <code>'a'</code>).
    </p>
  </div>
</div>

## Examples

Let's add a few variables to our code. In your `variables_activity.cpp` file, in the `variables_exploration` function definition, add the following lines of code:

```c
int currentLed = 1;
int currentNote = NOTE_C4;
int duration = 1000;
```

<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseVarNamingTricks" role="button" aria-expanded="false" aria-controls="collapseVarNamingTricks">
    More Details
  </a>
</p>
<div class="collapse" id="collapseVarNamingTricks">
  <div class="card card-body">
    <p>
        Hopefully it's obvious what our variables represent based on their names. Notice that we can set our variables equal to other variables! <code>currentNote</code> has the same value as <code>NOTE_C4</code>. If we add <code>speaker_play_note(currentNote, duration)</code> to our code, it's the same as adding <code>speaker_play_note(NOTE_C4, 1000)</code>. Middle C will be played for one second.
    </p>    
  </div>
</div>



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

<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseVarIncrTricks" role="button" aria-expanded="false" aria-controls="collapseVarIncrTricks">
    More Details
  </a>
</p>
<div class="collapse" id="collapseVarIncrTricks">
  <div class="card card-body">
    <p>
        As you probably guessed by the lights on your board turning on, adding <code>++</code> to our variable name (with a semicolon at the end) increments the number our variable represents by 1. This is exactly the same as if we had written <code>currentLed = currentLed + 1</code>. It's nice that we don't have to hard-code the LED numbers into our code to tell the <em>compiler</em> that we want to light them up. It makes our code a little easier to read.
    </p>    
  </div>
</div>

## Exploration

1. Divide `currentNote` by 2 using the following code snippet: `currentNote = currentNote / 2;` Play a sound again. How does our new sound compare to our old one?

1. See what happens if you multiply or divide `currentNote` by powers of 2 (2, 4, 8, 16) and use it to play a sound. For example, how does the sound compare to our old ones if we write `currentNote = currentNote * 8;`?
    <p hspace="3%">
    <a class="btn btn-primary" data-toggle="collapse" href="#collapseVarHint1" role="button" aria-expanded="false" aria-controls="collapseVarHint1">
        Hint
    </a>
    </p>
    <div class="collapse" id="collapseVarHint1">
    <div class="card card-body">
        When we divide and multiply the frequency of notes by powers of 2, we get "octaves". For Middle C, this means we get higher or lower C notes.
    </div>
    </div>

1. Light up three additional LEDs in the same way we did above.

## Challenges

**Challenge 1:** Light up all the LEDs on the board using the pattern above, then turn them all off again.

<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseVarHint2" role="button" aria-expanded="false" aria-controls="collapseVarHint2">
    Hint
  </a>
</p>
<div class="collapse" id="collapseVarHint2">
  <div class="card card-body">
    <p>
        We can use <code>currentNote--;</code> to decrement our variable by 1. This is the same as writing <code>currentNote = currentNote - 1;</code>
    </p>
  </div>
</div>

**Challenge 2:** Use the `currentNote` and `duration` variables to play notes with random sound lengths and frequencies

<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseVarHint3" role="button" aria-expanded="false" aria-controls="collapseVarHint3">
    Hint
  </a>
</p>
<div class="collapse" id="collapseVarHint3">
  <div class="card card-body">
    <p>
        You can use any mathematical expression you like and set your variable equal to it. For example: <code>duration = ((8 * 7) / 3) * 10;</code> or <code>currentNote = 2 * 2 * 2 + 1034;</code>
    </p>
  </div>
</div>

IMPORTANT: For your `variables_challenge1` and `variables_challenge2` functions, you will need to redeclare your variables. Variables live inside functions. If we are in a new function, the variable doesn't exist any more. Can you think of any other variables you might want to make?