---
layout: lab
toc: false
title: "Module 3: Sound"
short_title: Sound
icon: fa-solid fa-volume
order: 3
---

<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseBuzzerInfo" role="button" aria-expanded="false" aria-controls="collapseBuzzerInfo">
    Sounds on the Y-Badge
  </a>
</p>
<div class="collapse" id="collapseBuzzerInfo">
  <div class="card card-body">
    Your Y-Badge has a buzzer built into it. This buzzer is able to play single-note sounds by turning an electromagnet on and off at high speeds. The magnetic field that is produced vibrates a small disk very quickly, creating the sound you hear. We can specify the frequency of the buzzer in order to play different notes, and how long that note is played for. However, we can't specify the volume of the sound; it's fixed.
  </div>
</div>

<p align="center"><img src="{% link media/buzzer.png %}" width="400" hspace="5%" vspace="2%"/></p>

## Functions

The function to play a sound looks like this:
```c
speaker_play_note(<note>, <duration>);
```

<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseSoundFuncInfo" role="button" aria-expanded="false" aria-controls="collapseSoundFuncInfo">
    Explanation
  </a>
</p>
<div class="collapse" id="collapseSoundFuncInfo">
  <div class="card card-body">
    <ul>
        <li>
            The <code>&lt;note&gt;</code> should be a number that represents the frequency. For example, 262 could be used to play "middle C". We have created several constants that represent the values of these notes. For example, typing <code>NOTE_C4</code> in your code is the same as typing the number <code>262</code>. For a list of other note options, explore the <code>yboard.h</code> file.
        </li>
        <li>
            The <code>&lt;duration&gt;</code> should be the length you want the note to play in <em>milliseconds</em> (a duration of 1000 would play the note for one second).
        </li>
    </ul>
  </div>
</div>

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

    * The `speaker_play_note()` function is a **non-blocking** function, which means other functions that are called after it will actually run at the same time. However, the buzzer can only play one note at a time, so any additional `speaker_play_note()` calls will wait until the one before has finished.

## Challenges

**Challenge 1:** Experiment with the durations of the above song to add some rythm or adjust the speed of the song. How long the notes are played in comparison to each other can change how the song sounds (note how some notes are played twice as long as others above). Can you make the song twice as fast?

**Challenge 2:** Finish the rest of "Twinkle Twinkle Little Star" by adding more to the code.