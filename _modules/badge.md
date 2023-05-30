---
layout: lab
toc: false
title: "Module 7: Create Your Badge"
short_title: Create Your Badge
icon: fa-kit fa-y-badge
order: 7
---

<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseKnobInfo" role="button" aria-expanded="false" aria-controls="collapseKnobInfo">
    The Knob on the Y-Badge
  </a>
</p>
<div class="collapse" id="collapseKnobInfo">
  <div class="card card-body">
    <p>
        The knob is a device known as a <strong>potentiometer</strong>. We send a <em>voltage</em> through it and measure how much of that voltage is allowed to pass through, based on the position of the knob. This allows us to return a value based on the current position of the knob using the <code>knob_get()</code> function.
    </p>
  </div>
</div>

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

<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseKnobExample" role="button" aria-expanded="false" aria-controls="collapseKnobExample">
    More Details
  </a>
</p>
<div class="collapse" id="collapseKnobExample">
  <div class="card card-body">
    <p>
        You'll notice that we've multiplied the value of <code>knob_get()</code> by 255 and divided it by 100. The reason is because <code>leds_set_brightness()</code> needs a brightness between 0 and 255, but <code>knob_get()</code> gives us a value between 0 and 100. We can <em>scale</em> our value from <code>knob_get()</code> to a value that <code>leds_set_brightness()</code> will understand by <em>multiplying</em> it by the maximum value of our <em>brightness function</em> and <em>dividing</em> by the maximum value of our <em>knob function</em>.
    </p>
    <p>
        Notice also that we are monitoring the value of <code>knob_get()</code> continuously by placing it inside an infinite <code>while</code> loop.
    </p>
    <p>
        There are other things you can try to control with <code>knob_get()</code> (for example, you could use it to change the <em>color</em> of LEDs rather than brightness) but brightness is the easiest. Feel free to experiment with it!
    </p>
  </div>
</div>

## Design Your Own Y-Badge

Now it's your turn to customize your badge. Write code to make it your own. You could make it into a three-key piano, display a spectacular light show, or anything else. The possibilities are endless! Just be sure to put all the skills you've learned to good use!