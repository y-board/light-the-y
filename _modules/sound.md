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

Your Y-Badge has a buzzer built into it. This buzzer is able to play single-note sounds by turning an electromagnet on and off at high speeds. The magnetic field that is produced vibrates a small disk very quickly, creating the sound you hear. We can specify the frequency of the buzzer in order to play different notes, and how long that note is played for. However, we can't specify the volume of the sound; it's fixed.
</details>

<p align="center"><img src="{% link media/buzzer.png %}" width="400" hspace="5%" vspace="2%"/></p>

## Functions

The function to play a sound looks like this:
```c
speaker_play_note(<note>, <duration>);
```

<details markdown="block">
<summary markdown="span">Explanation
</summary>

* The `<note>` should be a number that represents the frequency. For example, 262 could be used to play "middle C". We have created several constants that represent the values of these notes. For example, typing `NOTE_C4` in your code is the same as typing the number `262`. For a list of other note options, explore the `ybadge.h` file.

* The `<duration>` should be the length you want the note to play in _milliseconds_ (a duration of 1000 would play the note for one second).
</details>

## Examples
To play a G5 for 1/4 second, you would write:

```c
speaker_play_note(NOTE_G5, 250)
```

To play "Twinkle Twinkle Little Star", you would use the following code:

```c
speaker_play_note(NOTE_C4, 400);
speaker_play_note(NOTE_C4, 400);
speaker_play_note(NOTE_G4, 400);
speaker_play_note(NOTE_G4, 400);
speaker_play_note(NOTE_A4, 400);
speaker_play_note(NOTE_A4, 400);
speaker_play_note(NOTE_G4, 800);
speaker_play_note(NOTE_F4, 400);
speaker_play_note(NOTE_F4, 400);
speaker_play_note(NOTE_E4, 400);
speaker_play_note(NOTE_E4, 400);
speaker_play_note(NOTE_D4, 400);
speaker_play_note(NOTE_D4, 400);
speaker_play_note(NOTE_C4, 800);
```


## Exploration

1. Make the speaker play a C note for 3 seconds and then stop. 

1. Make the speaker play C, D, E, D, C for 500ms each.

1. What happens if you try to call `leds_set_color(1, 255, 0, 0)` to turn LED 1 red right after you call `speaker_play_note(NOTE_C4, 5000)` to play middle C for 5 seconds? Does the board wait to turn the light on until the sound is done playing?
    <details markdown="block">
    <summary markdown="span">Why Does This Happen?
    </summary>
    
    The `speaker_play_note()` function is a **non-blocking** function, which means other functions that are called after it will actually run at the same time. However, the buzzer can only play one note at a time, so any additional `speaker_play_note()` calls will wait until the one before has finished.
    </details>

## Challenges

**Challenge 1:** Experiment with the durations of the above song to add some rythm or adjust the speed of the song. How long the notes are played in comparison to each other can change how the song sounds (note how some notes are played twice as long as others above). Can you make the song twice as fast?

**Challenge 2:** Finish the rest of "Twinkle Twinkle Little Star" by adding more to the code.