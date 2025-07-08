---
layout: lab
toc: false
title: "Module 11: Microphone"
short_title: Microphone
icon: fa-solid fa-microphone
order: 11
---

<details markdown="block">
<summary markdown="span">Recording Audio with the Y-Board</summary>
The Y-Board has a microphone on the top left corner. This microphone can be used to record audio. The audio is recorded in the `.wav` format, which is a common format for audio files. The data in the file represents a sound wave, similar to the audio files you can play on the Y-Board.
</details>

<p align="center"><img src="{% link media/wave.png %}" width="1000" hspace="5%" vspace="2%"/></p>

## Functions

The microphone has two functions that are used to start recording and to stop recording:

```cpp
Yboard.start_recording(<filename>);
Yboard.stop_recording();
```

The `start_recording` function takes a string argument that represents the name of the file you want to save the recording to. For example, to save the recording to a file called `myrecording.wav`, you would write `Yboard.start_recording("myrecording.wav")`. The `stop_recording` function stops the recording and saves the file.


## Examples

```cpp
// Start recording audio
Yboard.start_recording("test.wav");

// Wait for 5 seconds to record audio
delay(5000);

// Stop recording
Yboard.stop_recording();
```


## Exploration

1. Update the example above to record audio for 10 seconds instead of 5 seconds. How do you know when the recording has started and stopped? Update the LEDS to show you the status of the board.

2. Update the example above to start recording when a button is pressed.


## Challenges

**Challenge 1:** Write a program that records audio when a button is pressed, and stops recording when the button is released. Play back the recorded audio after the button is released. Turn the LEDs red while recording and green while playing back the audio.

**Challenge 2:** Write a program that uses one button to record audio and another button to play back the recorded audio. Update the display to show the status of the recording and playback (e.g., "Recording..." or "Playing...").
```
