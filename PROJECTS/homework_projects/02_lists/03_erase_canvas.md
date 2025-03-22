## Problem Statement

Implement an 'eraser' on a canvas.

The canvas consists of a grid of blue 'cells' which are drawn as rectangles on the screen. We then create an eraser rectangle which, when dragged around the canvas, sets all of the rectangles it is in contact with to white.

## Installation

To run this program, you need to install the `graphics.py` library. You can install it using:

```bash
pip install graphics.py
```

## Starter Code

```bash
def main():
    print("Delete this line and write your code here! :)")


# This provided line is required at the end of
# Python file to call the main() function.
if __name__ == '__main__':
    main()
```

## Solution

"""
This program implements an 'eraser' on a canvas.

The canvas consists of a grid of blue 'cells' which are drawn
as rectangles on the screen. We then create an eraser rectangle
which, when dragged around the canvas, sets all of the rectangles
it is in contact with to white.
"""

```bash
from graphics import GraphWin, Rectangle, Point, Text
import time

CANVAS_WIDTH: int = 400
CANVAS_HEIGHT: int = 400

CELL_SIZE: int = 40
ERASER_SIZE: int = 20


def erase_objects(cells, eraser):
    """Erase cells that overlap with the eraser by setting their fill to white."""
    eraser_p1 = eraser.getP1()
    eraser_p2 = eraser.getP2()
    left_x = eraser_p1.getX()
    top_y = eraser_p1.getY()
    right_x = eraser_p2.getX()
    bottom_y = eraser_p2.getY()

    # For every cell in the grid, check for overlap with the eraser
    for cell in cells:
        cell_p1 = cell.getP1()
        cell_p2 = cell.getP2()
        if (
            left_x < cell_p2.getX()
            and right_x > cell_p1.getX()
            and top_y < cell_p2.getY()
            and bottom_y > cell_p1.getY()
        ):
            cell.setFill("white")


def main():
    win = GraphWin("Eraser by Abdul Samad", CANVAS_WIDTH, CANVAS_HEIGHT)
    win.setBackground("white")

    num_rows = CANVAS_HEIGHT // CELL_SIZE
    num_cols = CANVAS_WIDTH // CELL_SIZE

    # Create a grid of blue squares
    cells = []
    for row in range(num_rows):
        for col in range(num_cols):
            left_x = col * CELL_SIZE
            top_y = row * CELL_SIZE
            right_x = left_x + CELL_SIZE
            bottom_y = top_y + CELL_SIZE

            cell = Rectangle(Point(left_x, top_y), Point(right_x, bottom_y))
            cell.setFill("blue")
            cell.setOutline("blue")
            cell.draw(win)
            cells.append(cell)

    # Display instructions
    instructions = Text(
        Point(CANVAS_WIDTH / 2, CANVAS_HEIGHT - 10),
        "Click anywhere to erase. Press any key to quit.",
    )
    instructions.setSize(10)
    instructions.draw(win)

    # Main loop - respond to clicks until user presses a key
    while win.checkKey() == "":
        # Wait for a click
        click = win.checkMouse()
        if click:
            # Create eraser at clicked position
            mouse_x = click.getX()
            mouse_y = click.getY()

            # Remove previous eraser if it exists
            try:
                eraser.undraw()
            except:
                pass

            # Create new eraser
            eraser = Rectangle(
                Point(mouse_x - ERASER_SIZE / 2, mouse_y - ERASER_SIZE / 2),
                Point(mouse_x + ERASER_SIZE / 2, mouse_y + ERASER_SIZE / 2),
            )
            eraser.setFill("pink")
            eraser.setOutline("red")
            eraser.draw(win)

            # Erase overlapping cells
            erase_objects(cells, eraser)

        time.sleep(0.01)  # Short delay

    win.close()


if __name__ == "__main__":
    main()
```
