---
layout: lab
toc: false
title: "Module 7: Knob"
short_title: Knob
icon: fa-solid fa-dial
order: 7
---

<details markdown-="block">
<summary markdown="span">The Knob on the Y-Board
</summary>

The knob is a device known as a **rotary encoder**. It can be turned left or right, and it can also be pressed down like a button. Every time the knob is turned, it sends a pulse to the  board so that it can keep track of how far it has been turned. While the knob can be turned left and right as much as you want, there is a value for how far it has been turned, postive for right and negative for left.
</details>

<p align="center"><img src="{% link media/knob.jpg %}" width="400" hspace="5%" vspace="10px"></p>

## Functions

There are a few functions that we can use to interact with the knob. To get the knob position, you can call `Yboard.get_knob()`. If you want to reset the knob position to zero, you can call `Yboard.reset_knob()`. If you want to check if the knob is pressed down, you can call `Yboard.get_knob_button()`.

## Examples

```cpp
Yboard.set_led_brightness(0);             // Set initial brightness to 0
Yboard.set_all_leds_color(255, 255, 255); // Set all LEDs to white

while(true) {
    int knob_position = Yboard.get_knob();

    // Make sure the knob value is not too low or too high.
    if (knob_position < 0) {
        knob_position = 0;
    } else if (knob_position > 100) {
        knob_position = 100;
    }

    int brightness = 255 * knob_position / 100;
    Yboard.set_led_brightness(brightness);

    delay(50);

    // Then use Yboard.set_led_color() as normal inside this loop.
}
```

<details markdown="block">
<summary markdown="span">More Details
</summary>
You'll notice that we've multiplied the value of `Yboard.get_knob()` by 255 and divided it by 100. The reason is because `Yboard.set_led_brightness()` needs a brightness between 0 and 255, but `Yboard.get_knob()` gives us a value between 0 and 100. We can _scale_ our value from `Yboard.get_knob()` to a value that `Yboard.set_led_brightness()` will understand by _multiplying_ it by the maximum value of our _brightness function_ and _dividing_ by the maximum value of our _knob function_.

Notice also that we are monitoring the value of `Yboard.get_knob()` continuously by placing it inside an infinite `while` loop.

There are other things you can try to control with `Yboard.get_knob()` (for example, you could use it to change the _color_ of LEDs rather than brightness) but brightness is the easiest. Feel free to experiment with it!
</details>

## Exploration

<details markdown="block">
<summary markdown="span">Remember to change `main.cpp` before continuing...
</summary>
> 📝 **_NOTE:_** You will need to go to `main.cpp` and change the comments to call the correct activity function:
```c
// conditionals_activity();
knob_activity();
```
</details>

1. Have the knob control the brightness of the LEDs. You can use the code example above to get started.

## Challenges

<details markdown="block">
<summary markdown="span">Remember to comment/uncomment the correct function calls...
</summary>
_Remember to comment out the `knob_exploration();` call in the `knob_activity` function and uncomment the correct challenge function:_

```c
knob_exploration();
// knob_challenge1();
// knob_challenge2();
```
</details>

**Challenge 1:** Light up the LEDs as you turn the knob. The LEDs should light up one by one as you turn the knob to the right, and turn off one by one as you turn the knob to the left.

**Challenge 2:** If switch 1 is on, have the knob control the red component of the LED color, if switch 2 is on, have the knob control the green component of the LED color, and if switch 3 is on, have the knob control the blue component of the LED color.
