---
layout: lab
toc: false
title: "Module 3: Sound"
short_title: Sound
icon: fa-solid fa-volume
order: 3
---

<details markdown="block">
<summary markdown="span">Sounds On The Y-Badge
</summary>
Y-Badge v3 has a speaker and Y-Badge v2 has a buzzer. Both can be used to play sounds. The speaker is able to play a wider range of sounds, but the buzzer is simpler to use. Both are able to play sounds by turning an electromagnet on and off at high speeds. The magnetic field that is produced vibrates a small disk very quickly, creating the sound you hear. We can specify the frequency of the buzzer in order to play different notes, and how long that note is played for.
</details>

<p align="center"><img src="{% link media/buzzer.png %}" width="400" hspace="5%" vspace="2%"/>
<br>
Y-Board v2 Buzzer. Y-Board v3 has a speaker.
</p>

## Functions

The function to play a sound looks like this:
```cpp
Yboard.play_note(<note>, <duration>);
```


* The `<note>` should be a number that represents the frequency. For example, 262 could be used to play "middle C". We have created several constants that represent the values of these notes. For example, typing `NOTE_C4` in your code is the same as typing the number `262`. For a list of other note options, explore the `ybadge.h` file.

* The `<duration>` should be the length you want the note to play in _milliseconds_ (a duration of 1000 would play the note for one second).

## Examples

To play a G5 for 1/4 second, you would write:

```cpp
Yboard.play_note(NOTE_G5, 250)
```

To play "Twinkle Twinkle Little Star", you would use the following code:

```cpp
Yboard.play_note(NOTE_C4, 400);
Yboard.play_note(NOTE_C4, 400);
Yboard.play_note(NOTE_G4, 400);
Yboard.play_note(NOTE_G4, 400);
Yboard.play_note(NOTE_A4, 400);
Yboard.play_note(NOTE_A4, 400);
Yboard.play_note(NOTE_G4, 800);
Yboard.play_note(NOTE_F4, 400);
Yboard.play_note(NOTE_F4, 400);
Yboard.play_note(NOTE_E4, 400);
Yboard.play_note(NOTE_E4, 400);
Yboard.play_note(NOTE_D4, 400);
Yboard.play_note(NOTE_D4, 400);
Yboard.play_note(NOTE_C4, 800);
```


## Exploration

<details markdown="block">
<summary markdown="span">Remember to change `main.cpp` before continuing...
</summary>
> 📝 **_NOTE:_** You will need to go to `main.cpp` and change the comments to call the correct activity function:
```c
// delay_activity();
sound_activity();
```
</details>

1. Make the speaker play a C note for 3 seconds and then stop. 

1. Make the speaker play C, D, E, D, C for 500ms each.

1. What happens if you try to call `Yboard.set_led_color(1, 255, 0, 0)` to turn LED 1 red right after you call `Yboard.play_note(NOTE_C4, 5000)` to play middle C for 5 seconds? Does the board wait to turn the light on until the sound is done playing?
    <details markdown="block">
    <summary markdown="span">Why Does This Happen?
    </summary>
    
    The `Yboard.play_note()` function is a **non-blocking** function, which means other functions that are called after it will actually run at the same time. However, the speaker can only play one note at a time, so any additional `Yboard.play_note()` calls will wait until the one before has finished.
    </details>

## Challenges

<details markdown="block">
<summary markdown="span">Remember to comment/uncomment the correct function calls...
</summary>
_Remember to comment out the `sound_exploration();` call in the `sound_activity` function and uncomment the correct challenge function:_

```c
sound_exploration();
// sound_challenge1();
// sound_challenge2();
```
</details>

**Challenge 1:** Experiment with the durations of the above song to add some rythm or adjust the speed of the song. How long the notes are played in comparison to each other can change how the song sounds (note how some notes are played twice as long as others above). Can you make the song twice as fast?

**Challenge 2:** Finish the rest of "Twinkle Twinkle Little Star" by adding more to the code.
