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

The knob is a device known as a **potentiometer**. We send a _voltage_ through it and measure how much of that voltage is allowed to pass through, based on the position of the knob. This allows us to return a value based on the current position of the knob using the `Yboard.get_knob()` function.

</details>

<p align="center"><img src="{% link media/knob.png %}" width="400" hspace="5%" vspace="10px"></p>

## Functions

We can use the value returned from the `Yboard.get_knob()` function to change the brightness of the LEDs on our board. This is the code:

```cpp
while(true) {
    int brightness = 255 * Yboard.get_knob() / 100;
    Yboard.set_led_brightness(brightness);

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
