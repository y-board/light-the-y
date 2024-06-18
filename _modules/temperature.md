---
layout: lab
toc: false
title: "Module 7: Temperature and Humidity Sensor"
short_title: Temperature Sensor
icon: fa-solid fa-temperature-three-quarters
order: 7
---

<details markdown="block">
<summary markdown="span">Temperature and Humidity Sensor on the Y-Badge
</summary>

There is a temperature and humidity sensor on the Y-Badge board. This sensor is used to measure the temperature and humidity of the environment around the board.
</details>

<p align="center"><img src="{% link media/buttons_and_switches.png %}" width="400" hspace="5%" vspace="2%"/></p>

## Functions

The function to read the temperature and humidity is:

```cpp
Yboard.get_temperature();
```

This function returns a `temperature_data` `struct` that contains the temperature and humidity values. The temperature is in degrees Celsius and the humidity is a percentage. A C `struct` is a way to group related variables together. Here is the definition of the `temperature_data` `struct`:

```cpp
struct temperature_data {
    float temperature;
    float humidity;
};
```

To access the temperature and humidity values, you can use the `.` operator:

```cpp
temperature_data data = Yboard.get_temperature();
float temperature = data.temperature;
float humidity = data.humidity;
```

<details markdown="block">
<summary markdown="span">&deg;C to &deg;F Conversion
</summary>
The sensor reports the temperature in degrees Celsius. If you want to convert the temperature to degrees Fahrenheit, you can use the following formula:

\\[
T_{\text{F}} = T_{\text{C}} \times \frac{9}{5} + 32
\\]

where $$T_{\text{F}}$$ is the temperature in degrees Fahrenheit and $$T_{\text{C}}$$ is the temperature in degrees Celsius.
</details>

## Examples
Here is an example of using the temperature sensor to control an LED. If the temperature is above 25&deg;C (77&deg;F), the LED will turn red, otherwise it will turn blue. The temperature is read every second.

```cpp
while(true) {
    temperature_data data = Yboard.get_temperature();

    if(data.temperature > 25) {
        Yboard.set_led_color(1, 255, 0, 0);
    } else {
        Yboard.set_led_color(1, 0, 0, 255);
    }

    delay(1000);
}
```

You can breath on the sensor or put your finger on it to make the temperature go up fast.

## Exploration
<details markdown="block">
<summary markdown="span">Remember to change `main.cpp` before continuing...
</summary>
> 📝 **_NOTE:_** You will need to go to `main.cpp` and change the comments to call the correct activity function.
</details>

1. Print the temperature and humidity values to the serial monitor. What is the temperature and humidity in the room you are in right now?

2.  What are the values when you breathe on the sensor or put your finger on it?


## Challenges

_Remember to comment out the `temperature_exploration();` call in the `temperature_activity` function and uncomment the correct challenge function:_

```c
// temperature_exploration();
temperature_challenge1();
```

**Challenge 1:** Using the information you gathered in the exploration section, create a program that turns on the LEDs based on how hot the temperature is relative to the ambient temperature and maximum temperature you saw. For example, if the temperature is close to the ambient temperature, turn on the first LED. As it gets hotter, turn on more LEDs until you reach the maximum temperature and all the LEDs are on.
