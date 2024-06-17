---
layout: lab
toc: false
title: "Module 7: Audio Files"
short_title: Audio Files
icon: fa-solid fa-file-audio
order: 7
---

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

You can download sound files from the internet. There are many websites that offer free sound files, such as [freesound.org](https://freesound.org/). 

You will need to convert the sound files to the `.wav` format before you can use them on the Y-Board.  To convert a sound file to the `.wav` format:
1. Open the *Audacity* program on the computer.
1. Import the sound file into Audacity.
1. Export the sound file as a `.wav` file, selecting *Mono*, *16-bit PCM*, and *16000 Hz* as the format.

## Exploration




