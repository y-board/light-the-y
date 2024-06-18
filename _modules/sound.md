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

### Single Notes

The function to play a sound looks like this:
```cpp
Yboard.play_note(<note_frequency>, <duration>);
```


* The `<note>` should be a number that represents the frequency. For example, 262 could be used to play "middle C". We have created several constants that represent the values of these notes. For example, typing `NOTE_C4` in your code is the same as typing the number `262`. For a list of other note options, explore the `ybadge.h` file.

* The `<duration>` should be the length you want the note to play in _milliseconds_ (a duration of 1000 would play the note for one second).

This function above is a **blocking** function, which means that the code will wait until the sound is done playing before moving on to the next line of code. If you want to start playing a sound and then do something else at the same time, you can use the following function:
```cpp
Yboard.play_note_background(<note_frequency>, <duration>);
```
If you call this function multiple times, the notes will be queued up and played one after the other in the background.

### Sequences of Notes

You can also play a sequence of notes by using the following functions (either blocking, or in the background)
```cpp
Yboard.play_notes(<string>);
Yboard.play_notes_background(<string>);
```

The text string supports the following characters:

| Character | Description |
|-----------|-------------|
A–G	                | Specifies a note that will be played. |
R                   | Specifies a rest (no sound for the duration of the note).|
+ or # after a note | Raises the preceding note one half-step (sharp).|
- after a note      | Lowers the preceding note one half-step.
> after a note	    | Plays the note one octave higher (multiple >’s can be used, eg: C>>)
< after a note	    | Plays the note one octave lower (multiple <’s can be used, eg: C<<)
1–2000 after a note	| Determines the duration of the preceding note. For example, C16 specifies C played as a sixteenth note, B1 is B played as a whole note. If no duration is specified, the note is played as a quarter note. |
O followed by a # | Changes the octave. Valid range is 4-7. Default is 5.
T followed by a # |   Changes the tempo. Valid range is 40-240. Default is 120.
V followed by a # |   Changes the volume.  Valid range is 1-10. Default is 5.
!                 |  Resets octave, tempo, and volume to default values.
spaces            |   Spaces can be placed between notes or commands for readability, but not within a note or command (eg: `"C4# D4"` is valid, `"C 4 # D 4"` is not. `"T120 A B C"` is valid, `"T 120 A B C"` is not).

### Checking if the Sound is Done

The following function will return `true` if the sounds is still playing, and `false` if it is done:
```cpp
Yboard.is_audio_playing();
```
You may need to learn about [loops]({% link _modules/loops.md %}) and [conditional statements]({% link _modules/conditionals.md %}) before you can use this function in your code.


## Examples

To play a G5 for 1/4 second, you would write:

```cpp
Yboard.play_note(NOTE_G5, 250)
```

To play "Twinkle Twinkle Little Star" in the background, you could use the following code:

```cpp
Yboard.play_notes_background("O4 CCGGAAG2 FFEEDDC2");
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

1. What happens if you try to call `Yboard.set_led_color(1, 255, 0, 0)` to turn LED 1 red right after you call `Yboard.play_note_background(NOTE_C4, 5000)` to play middle C for 5 seconds? Does the board wait to turn the light on until the sound is done playing?
    <details markdown="block">
    <summary markdown="span">Why Does This Happen?
    </summary>
    
    The `Yboard.play_note_background()` function is a **non-blocking** function, which means other functions that are called after it will actually run at the same time. However, the speaker can only play one note at a time, so any additional `Yboard.play_note_background()` calls will wait until the one before has finished.
    </details>

1. Play a scale of notes in Octave 5.  Then play the same scale in Octave 6, but at double the tempo.

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

**Challenge 3:** Look up the notes to a song you like and try to play it on the Y-Board. You can use the `play_notes` function to play the song in the background while you do other things.
