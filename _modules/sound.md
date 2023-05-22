---
layout: lab
toc: false
title: "Module 3: Sound"
short_title: Sound
icon: fa-solid fa-volume
order: 3
---

## Sounds on the Y-Badge

Your Y-Badge has a buzzer built into it. This buzzer is able to play single-note sounds by turning an electromagnet on and off at high speeds. The magnetic field that is produced vibrates a small disk very quickly, creating the sound you hear. We can specify the note the buzzer plays, and how long that note is played for. However, we can't specify the volume of the sound; it's fixed.

<img src="{% link media/buzzer.png %}" width="400" hspace="5%" vspace="10px">

## Functions

The function to play a sound looks like this:
```c
speaker_play_note(<note>, <duration>);
```

* The `<note>` should be a constant value that we've defined for you (for example, NOTE_C4, which would play a middle C). For a list of other note options, explore the `yboard.h` file.
* The `<duration>` should be the length you want the note to play in _milliseconds_ (a duration of 1000 would play the note for one second).

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

## Challenges

1. Experiment with the durations of the above song to add some rythm or adjust the speed of the song. How long the notes are played in comparison to each other can change how the song sounds (note how some notes are played twice as long as others above). Can you make the song twice as fast?

1. Finish the rest of "Twinkle Twinkle Little Star" by adding more to the code.