---
layout: lab
toc: false
title: "Module 8: Display"
short_title: Display
icon: fa-solid fa-display
order: 8
---

<details markdown="block">
<summary markdown="span">Display On The Y-Board
</summary>
Y-Board has a single color display that is 128 pixels wide and 64 pixels long. You can use it to display text, shapes, and other graphics. The display is controlled by the `Yboard` object, which provides functions to draw on the display.
</details>

<p align="center"><img src="{% link media/wave.png %}" width="1000" hspace="5%" vspace="2%"/></p>

## Functions

Interacting with the display is slightly different from the other modules. Since there are so many functions associated with the display, we decided to have you access the display object directly, rather than through functions the Y-Board provides. The display object is called `display`, and it has the following functions:

- `Yboard.display.display()`: This must be called to update the display after making changes. It refreshes the display with the current content.
- `Yboard.display.clear()`: Clears the display.
- `Yboard.display.set_cursor(x, y)`: Sets the cursor position to the specified coordinates `(x, y)`, where `x` is the horizontal position and `y` is the vertical position. The top-left corner is `(0, 0)`, and the bottom-right corner is `(127, 63)`.
- `Yboard.display.println(<string>)`: Prints the specified string at the current cursor position.
- `Yboard.display.draw_line(x1, y1, x2, y2)`: Draws a line from the point `(x1, y1)` to the point `(x2, y2)`.
- `Yboard.display.draw_rect(x, y, width, height)`: Draws a rectangle with the top-left corner at `(x, y)`, with the specified `width` and `height`.
- `Yboard.display.fill_rect(x, y, width, height)`: Fills a rectangle with the top-left corner at `(x, y)`, with the specified `width` and `height`.
- `Yboard.display.draw_circle(x, y, radius)`: Draws a circle with the center at `(x, y)` and the specified `radius`.
- `Yboard.display.fill_circle(x, y, radius)`: Fills a circle with the center at `(x, y)` and the specified `radius`.

## Examples
```cpp
// Clear the display
Yboard.display.clear();
// Set the cursor to the center of the display
Yboard.display.set_cursor(64, 32);
// Print "Hello, World!" at the center of the display
Yboard.display.println("Hello, World!");
// Display the changes
Yboard.display.display();
```

## Exploration

1. Write a program that displays your name on the display, centered vertically and horizontally.
2. When a button is pressed, display a message on the display that says "Button Pressed!" and then clear the display after 2 seconds.

## Challenges

**Challenge 1:** Write a program that displays the state of all the buttons and switches on the display.
