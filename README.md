# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver
Submitting this project a few days late so at this point did not go beyond the specific assignment. Look forward to spending more time on other assignments time permitting.

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Naked Twins is constraint similar to Eliminate and Only Choice: when there are two identical values of two digits each for boxes in a unit, while we don't which digits belong to which box, we do know that no other box in the unit can contain either of the two digits. We use constraint propagation by searching all units in the puzzle, finding instances of twins:
```python
vals = [values[box] for box in unit]
twins = [box for box in unit if len(values[box])==2 and vals.count(values[box])==2]
```
then removing the twin digits in any other box:
```python
  if (box not in twins and d in values[box]):
    values[box] = values[box].replace(d,"")
```
This effectively propagates the Naked Twins constraint and further reduces the puzzle.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: By adding the diagonal units to the unitlist, we apply the same constraint propagation used for other units (row, column and square) to the diagonal units. Each algorithm that applies constraint propagation including Eliminate, Only Choice and Naked Twins all operate on units and box peers. By adding diagonal units, these algorithms now see boxes along the two diagonal axis as peers, applying the unit constraints: all digits must be represented once and only once in the unit, in this case the diagonal unit. Modifying for Diagonal Sudoku didn't require making any changes to the algorithms, but rather adding diagonals to the unitlist:
```python
diagonal_units= [[],[]]
for idx, val in enumerate(cols):
    diagonal_units[0].append(rows[idx]+val)
for idx, val in enumerate(rows[::-1]):
    diagonal_units[1].append(val+cols[idx])
```
As with all things, im sure there is a way to write this much more simply. Feedback welcome!

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project.
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.
