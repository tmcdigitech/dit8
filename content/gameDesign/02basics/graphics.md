---
title: Drawing graphics
weight: 3
---

To create graphics for our games we will use the Pygame Zero library. You will find the documentation on the website useful!

The smallest square that can be displayed on a monitor is called a pixel. This diagram shows a close-up view of a window that is 40 pixels wide and 40 pixels high. At normal size you will not see the grid lines.

Model View Controller
Fig. 4.1 Model View Controller

We can refer to any pixel by giving two co-ordinates, (x,y) Make sure you understand co-ordinates before moving on because everything we do in Pygame Zero will use it. (In maths this called a ‘Cartesian coordinate system’).

## Lines and circles
If are using the Mu editor, Pygame Zero is built-in, but you must remember to click ‘Mode’ and select ‘Pygame Zero’ before running your program!

If you are using a different editor, instructions are online.

Program 4.1 Lines and circles
```python {linenos=table}
WIDTH = 500  # What are these units? What if we change them?
HEIGHT = 500  # What if we delete this line?


def draw():
    screen.clear()
    screen.draw.circle((250, 250), 50, "white")
    screen.draw.filled_circle((250, 100), 50, "red")
    screen.draw.line((150, 20), (150, 450), "purple")
    screen.draw.line((150, 20), (350, 20), "purple")
```
### Exercise

Finish drawing this picture

### Exercise

Draw your own picture.


## Moving rectangles
To make things move we need to add the special update() function. We don’t need to write our own loop because Pygame Zero calls this function for us in its own loop, over and over, many times per second.

Program 4.2 Moving rectangles
```python {linenos=table}
WIDTH = 500
HEIGHT = 500

box = Rect((20, 20), (50, 50))

def draw():
    screen.clear()
    screen.draw.filled_rect(box, "red")


def update():
    box.x = box.x + 2
    if box.x > WIDTH:
        box.x = 0
```
### Exercise

Make the box move faster.

### Exercise

Make the box move in different directions.

### Exercise

Make two boxes with different colours.




```python {linenos=table}
import pgzrun

WIDTH = 800
HEIGHT = 600

pgzrun.go() # Must be last line
```

## Background
Now let's add a coloured background. To do this we need to define a function called `draw()`, which Pygame Zero will call every time it needs to redraw the screen:

```python {linenos=table,hl_lines=["6-8"]}
import pgzrun

WIDTH = 800
HEIGHT = 600

def draw():
    screen.fill((128, 0, 0))

pgzrun.go() # Must be last line
```

{{< hint info >}}
**Why the double brackets?**\
Notice that we had to use two sets of brackets in that example to set the colour of the background. In Pygame Zero, colours are always written as a set of three numbers like this: `(0, 130, 255)`, which in Python is called a **tuple** (rhyming with 'couple'). A tuple is indicated with round brackets. But the function also takes a set of round brackets, so we know it is a function. So the outer set of brackets belongs to the `fill()` function call, and the inside set to the tuple for the colour.
{{< /hint >}}

## Basic shapes

Let's add a couple of basic shapes.

```python {linenos=table,hl_lines=[8]}
import pgzrun

WIDTH = 800
HEIGHT = 600

def draw():
    screen.fill((128, 0, 0))
    screen.draw.filled_circle((0,150), 10, (200, 100, 200))

pgzrun.go() # Must be last line
```

The `filled_circle()` command takes three bits of information, known as [arguments]({{< relref "/glossary/argument" >}}):
1. the co-ordinates of the circle's centre `(x, y)` as a tuple,
2. the radius,
3. the colour `(r, g, b)` as a tuple.

