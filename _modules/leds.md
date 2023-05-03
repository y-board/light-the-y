---
layout: lab
toc: false
title: "Module 1: LEDs"
short_title: LEDs and Functions
number: 1
order: 1
---

### LEDs on the Y-Badge

There are 20 LEDs on the Y-badge circuit board.  Each of these LEDs are RGB (red-green-blue) LEDs, meaning that they are made up of three smaller red, green and blue lights.  For each LED, you can set the brightness of the RGB pixels, making the LED appear to be any color you like.


## Functions

To make things happen on the Y-badge, you will need to call **functions** from your code.

The function to set an LED color looks like this:
```c
leds_set_color(<LED number>, <red>, <green>, <blue>)
```

The <red>, <green> and <blue> values represent the brightness of that color and can be any value from 0 to 255.

For example, to make LED3 display bright red, you should use this statement in your code (don't forget to add the semicolon):

```c
leds_set_color(3, 255, 0, 0);
```

To make LED15 display bright yellow, you should turn on the red and green pixels to max brightness:
```c
leds_set_color(15, 255, 255, 0);
```


## Questions
1. Find your favorite RGB color.

1. What happens if you (255, 255, 255) or (0, 0, 0)

## Challenges
1. Turn on LEDs 1, 13, and 17. Make them 3 different colors.

1. Turn on LED5 as red. Wait 2 seconds and then turn it off and immediately turn on LED6 as red. Wait 2 seconds and move the red light to LED7. Repeat this delay and move the red light to LED8, then LED9, then off.

1. Make the speaker play a C note for 3 seconds and then stop. 

1. Make the speaker play C, D, E, D, C for 500ms each.