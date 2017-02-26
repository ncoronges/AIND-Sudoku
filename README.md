# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver
Submitting this project a few days late so at this point did not go beyond the specific assignment. Look forward to spending more time on other assignments time permitting.

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: naked_twins() works very similarly to eliminate(). We look for instances where there are two identical values, each with two digits in a box within a unit, then we remove any instances of those digits from all the other boxes within the unit.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: The existing functions (eliminate and only_choice) apply constraint propagation (ensuring all digits are represented only once per unit). By adding the diagonal units to the unitlist, we apply the same constraint
propagation to the 2 diagonal rows.

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
