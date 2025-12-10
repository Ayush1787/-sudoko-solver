# -sudoko-solver
An interactive Sudoku Solver built with Python and Tkinter. Features a clean 9×9 grid, input validation, instant and step-by-step solving using a recursive backtracking algorithm, and real-time visual updates. A simple yet powerful tool to learn logic and algorithm design.


Step 1: Set Up Your Environment
Ensure Python is installed on your system.
You don’t need to install any external libraries—only the built-in tkinter and time modules are used.
You can run the project in a Python file (.py) or in a Jupyter Notebook with GUI support.

Step 2: Import Required Modules
import tkinter as tk
from tkinter import messagebox
import time
tkinter is used for building the GUI.

messagebox is used to display error or success messages.
time is used to add delay in step-by-step solving.

Step 3: Create the Main Application Window
Initialize a Tkinter window using Tk().
Set its title, dimensions, and background color.
Create a 9×9 grid of Entry widgets for user input.
Alternate the background color of cells to differentiate 3×3 blocks.

Step 4: Create a Grid Data Structure
Store the Entry widgets in a 2D list for easy access.
This grid allows reading and writing values to the puzzle cells.

Step 5: Add a Function to Retrieve Grid Input
Define a function get_grid() that:
Loops through each entry field.
Converts valid numbers to integers.
Flags invalid or empty inputs and alerts the user.

Step 6: Implement the Backtracking Algorithm
Define two functions:
is_valid() checks whether a number can be placed in a specific row, column, and 3×3 box.
solve_board() uses recursion to try numbers from 1 to 9 in each empty cell.
Add an optional animation mode using time.sleep() and GUI update calls to show step-by-step solving.

Step 7: Create a Function to Display the Solved Board
Once solved, populate each cell in the GUI with the correct number.
Reset the background color of each cell.

Step 8: Add Buttons for User Interaction
Add the following buttons below the Sudoku grid:
Solve Instantly: Solves the puzzle without delay.
Solve Step-by-Step: Shows solving visually with animation.
Clear: Clears all entries to allow new input.

Step 9: Bind Button Functions
Each button calls its respective function (solve(), clear()).
The solve function calls the solver and handles invalid or unsolvable puzzles.

Step 10: Run the Tkinter Main Loop
Use root.mainloop() to start the GUI event loop.
This keeps the window responsive and handles all user interactions.

code explanation
1.Import Modules
The code starts by importing necessary modules:
tkinter for creating the GUI,

messagebox for displaying alerts to the user,
time for adding delays in animated solving.

import tkinter as tk
from tkinter import messagebox
import time

2.Create Main Window and Grid
A Tk window is created and titled. A 9×9 grid of Entry widgets is initialized using a nested loop. These widgets are stored in a 2D list for easy reference. Each cell is assigned a background color to visually group 3×3 subgrids.
entries = [[None for _ in range(9)] for _ in range(9)]

3.Color Function
The function get_bg_color(i, j) returns alternating colors based on the position in the 3×3 block for better visual clarity of the grid.

4.Get Grid Function
get_grid() reads the current values from all entry widgets. If a cell is empty, it records zero. If an invalid character is entered, it highlights the cell and shows an error message.

5.Validity Check
The is_valid() function checks whether placing a number at a given row and column violates Sudoku rules (no duplicates in row, column, or 3×3 box).

6.Backtracking Solver
solve_board() is a recursive function implementing backtracking:
It searches for an empty cell.
Tries numbers 1 through 9.
If a valid number is found, it is placed and the function is called recursively.
If the puzzle reaches a dead end, it backtracks by resetting the cell to zero.
Optionally, visual updates and delays show the solving process step-by-step.

7.Display Solution
display_solution() updates the GUI cells with the final solved values and resets their background to original.

8.Solve Function
solve() collects the input grid, runs the solver, and updates the GUI with the solution. If the puzzle is invalid or unsolvable, it shows an error popup.

9.Clear Function
clear() resets the entire grid by deleting all cell entries and restoring their original background colors.

10.Buttons and Layout
Three buttons are added:
“Solve Instantly”: solves without delay,
“Solve Step-by-Step”: enables solving with visual effect,
“Clear”: resets the grid.
These buttons are arranged below the Sudoku grid.

11.Start GUI
root.mainloop() is called to start the Tkinter event loop, keeping the GUI window active and responsive to user interactions.
