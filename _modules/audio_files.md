---
layout: lab
toc: false
title: "Module 9: Audio Files"
short_title: Audio Files
icon: fa-solid fa-file-audio
order: 9
---

<div class="alert alert-warning" role="alert">
<i class="fa-duotone fa-triangle-exclamation"></i>
This module only works with **Y-Board v3**.
</div>

<details markdown="block">
<summary markdown="span">Sounds Files On The Y-Board
</summary>
The Y-Board v3 has a speaker and an SD card reader, allowing you to play audio files from the SD card.  These files are in the `.wav` format, which is a common format for audio files. The data in the file represents a sound wave, as shown below.  
</details>

<p align="center"><img src="{% link media/wave.png %}" width="1000" hspace="5%" vspace="2%"/>
<br>
WAVE file that represents a sound wave.
</p>

## Functions

The function to play an audio file looks like this:
```cpp
Yboard.play_sound_file(<filename>);
```

The filename argument is a string that represents the name of the file you want to play. For example, to play a file called `mysound.wav` in the `sounds` directory on the SD card, you would write `Yboard.play_sound_file("sounds/mysound.wav")`.

The above function is blocking, which means that the code will wait until the sound file is done playing before moving on to the next line of code. If you want to play a sound file in the background while other code runs, you can use the following function:

```cpp
Yboard.play_sound_file_background(<filename>);
```

You can also change the volume of the sound file using the following function, which takes a value from 0 to 10:

```cpp
Yboard.set_sound_file_volume(<volume>);
```

## Obtaining Sound Files

You can download sound files from the internet. There are many websites that offer free sound files, such as [freesound.org](https://freesound.org/) (note: this website requires you to create an account to download the audio files). 

You will need to convert the sound files to the correct `.wav` format before you can use them on the Y-Board.  To convert a sound file to the `.wav` format:
1. Open the *Audacity* program on the computer.
1. Import the sound file into Audacity (Select *File*->*Open* and choose the sound file you downloaded).
1. Export the sound file as a `.wav` file, by selecting *File*->*Export Audio*, and choosing a filename and folder to save the file.
1. In the *Export Audio* dialog box, choose the following settings:
    * Format: WAV (Microsoft)
    * Channels: Mono
    * Sample Rate: 16000 Hz
    * Encoding: Signed 16-bit PCM

        <img src="{% link media/audacity_export.png %}" width="700 "/>
1. Click *Export* 
1. Copy the `.wav` file to the SD card.

## Exploration
1. Find a sound file at [freesound.org](https://freesound.org/), download it, and convert it to the correct format.  Play the sound file on the Y-Board.

1. Update your program to play the sound file when a button is pressed, but only if switch 1 is up.  If switch one is slid down, stop playing the sound file.

## Challenge

1. Create a program that plays different sound effects on the Y-board depending on which button is pressed and how the switches are set.  

1. Can you create a program that plays a sound effect when you shake the Y-Board? 

1. Can you create a program that plays a song louder or quieter depending on the position of the knob?  (You can read about the knob in the [Create Your Badge]({% link _modules/badge.md %}) module). 




