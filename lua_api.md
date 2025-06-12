# Lua API
---

> **NOTE** : The lua runtime used to execute all lua code is sandboxed this means removal of most libaries deemed unsafe io, os, etc. Some libaries that could be deemed safe I have chosen to remove and replace with my own just in case or for ease of use.

> **NOTE** : The following APIs are unfinished new methods will be added and current ones may change.

---

## Drawing API

* ### Color
    * `rgb(red, green, blue)` - returns a color object that is passed to other methods.
    * `rgba(red, green, blue, alpha)` - returns a color object that is passed to other methods.
    * `gray(value, alpha = 255)` - returns a color object that is passed to other methods.
    * `hsb(hue, staturation, brightness)` - returns a color object that is passed to other methods.
    * `random_color()` - returns a random color as a color object.

* ### Shapes
    * `rect(x, y, width, height)` - draws a rectangle.
    * `circle(x, y, raius)` - draws a circle.
    * `ellipse(x, y, width, height)` - draws a ellipse.
    * `line(x1, y1, x2, y2)` - draws a line.

* ### Styling
    * `fill(color)` - fills shape(s) soild with the provided color.
    * `no_fill()` - removes the soild fill from the shape(s).
    * `stroke(color)` - sets the solid stroke color of the shape(s).
    * `no_stroke()` - removes the soild stroke from the shape(s).
    * `stroke_width(width)` - sets the stroke width of the shape(s).
    * `stroke_width()` - resets/disables the stroke width.
    * `stroke_dash(dash_array)` - sets the stroke to have dashes works on the stroke of all shapes.
    * `background(color)` - sets a background color for the canvas on the current frame.

---

## Frames API
* `new_frame()` - must be called atleast once to use any `Drawing API` methods as well as be called for each frame that you want added to a GIF/Video. when called automatically sets it as the current frame to edit.
* `current_frame()` - returns the index of the current frame.
* `set_frame(index)` - sets the frame you want to edit.
* `frame_count()` - returns the total number of frames.

---

## Exporting API
* `export_png(file_name, index = 0)` - given a index of a frame will export it as a png.
* `export_svg(file_name, index = 0)` - given a index of a frame will export it as a svg.
* `export_gif(file_name, duration = 100)` - exports all frames in order as a gif each frame will last `duration` which is in miliseconds.

---

## Math API
* `sin()`
* `cos()`
* `radians(degrees)`
* `degrees(radians)`