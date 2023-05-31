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

We can use the value returned from the `knob_get()` function to change the brightness of the LEDs on our board. This is the code:

```c
while(true) {
    int brightness = 255 * knob_get() / 100;
    leds_set_brightness(brightness);

    //then use leds_set_color() as normal inside this loop.
}
```

<details markdown="block">
<summary markdown="span">Read More
</summary>
You'll notice that we've multiplied the value of `knob_get()` by 255 and divided it by 100. The reason is because `leds_set_brightness()` needs a brightness between 0 and 255, but `knob_get()` gives us a value between 0 and 100. We can _scale_ our value from `knob_get()` to a value that `leds_set_brightness()` will understand by _multiplying_ it by the maximum value of our _brightness function_ and _dividing_ by the maximum value of our _knob function_.

Notice also that we are monitoring the value of `knob_get()` continuously by placing it inside an infinite `while` loop.

There are other things you can try to control with `knob_get()` (for example, you could use it to change the _color_ of LEDs rather than brightness) but brightness is the easiest. Feel free to experiment with it!
</details>

## Design Your Own Y-Badge

Now it's your turn to customize your badge. Write code to make it your own. You could make it into a three-key piano, display a spectacular light show, or anything else. The possibilities are endless! Just be sure to put all the skills you've learned to good use!