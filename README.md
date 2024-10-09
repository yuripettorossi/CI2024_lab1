# CI2024_lab1
This repository contains a notebook with the solution of the first laboratory assignement of the course "Computational Intelligence" by politecnico di Torino, academic year 2024/2025.

This Laboratory focuses on the problem of "Set Covering". (https://en.wikipedia.org/wiki/Set_cover_problem) for more information.

The set-cover.ipynb file contains the solution to six different instances of the problem, with different Universe size and number of Sets.

The main function of the file is the climb function.
It implements a Simulated Annealing Hill Climbing, with the option to combine it with the Steepest-step strategy.
The tweak is executed by permuting a roandom number of elements of the current solution; this number is regulated by a parameter of the function, that can be scheduled during the execution of the search, to balance between Exploration and Exploitation.




