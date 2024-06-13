---
layout: lab
toc: false
title: "Module 7: Create Your Badge"
short_title: Create Your Badge
icon: fa-kit fa-y-badge
order: 7
---

<details markdown-="block">
<summary markdown="span">The Knob on the Y-Badge
</summary>

The knob is a device known as a **potentiometer**. We send a _voltage_ through it and measure how much of that voltage is allowed to pass through, based on the position of the knob. This allows us to return a value based on the current position of the knob using the `knob_get()` function.

</details>

<p align="center"><img src="{% link media/knob.png %}" width="400" hspace="5%" vspace="10px"></p>

## Functions

We can use the value returned from the `Yboard.get_knob()` function to change the brightness of the LEDs on our board. This is the code:

```cpp
while(true) {
    int brightness = Yboard.get_knob();
    Yboard.set_led_brightness(brightness);

    // then use Yboard.set_led_color() as normal inside this loop.
}
```

## Design Your Own Y-Badge

Now it's your turn to customize your badge. Write code to make it your own. You could make it into a three-key piano, display a spectacular light show, or anything else. The possibilities are endless! Just be sure to put all the skills you've learned to good use!

<details markdown="block">
<summary markdown="span">Remember to change `main.cpp` before continuing...
</summary>
> 📝 **_NOTE:_** You will need to go to `main.cpp` and change the comments to call the correct activity function:
```c
// conditionals_activity();
badge_activity();
```
</details>
