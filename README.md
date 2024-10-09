# CI2024_lab1
This repository contains a notebook with the solution of the first laboratory assignement of the course "Computational Intelligence" by politecnico di Torino, academic year 2024/2025.

This Laboratory focuses on the problem of "Set Covering". (https://en.wikipedia.org/wiki/Set_cover_problem) for more information.

The set-cover.ipynb file contains the solution to six different instances of the problem, with different Universe size and number of Sets.

-Climb function
The main function of the file is the climb function.
It implements a Simulated Annealing Hill Climbing, with the option to combine it with the Steepest-step strategy.
The tweak is executed by permuting a roandom number of elements of the current solution; this number is regulated by a parameter of the function, that can be scheduled during the execution of the search, to balance between Exploration and Exploitation.

-Climb function: Details

climb(num_steps=10_000, num_samples=1, prob=0.75, n_prob_schedule=30, temperature=None, plot=False) -> tuple(Bool, Float)

parametrs:
num_steps:int, default=100
  The numbers of step evaluated before stopping the algorithm.

num_samples:int, default=1
  The number of neighbour solution evaluated to find the best step to perform in the Steepest-step strategy.
  If set to 1, no Steepest-step is performed.

prob:float, default=0.75
  prob is passed to the tweak function to calculate the number of elements of the current solution to be permuted to generate the next state.
  The elements are permuted using the following snippet of code:
        while tweaked==0 or np.random.random() < prob:
          random_index = np.random.randint(0,NUM_SETS)
          new_solution[random_index] = 1-new_solution[random_index]
          tweaked = 1
  The closer prob is to 1, the bigger will be the number of elements that get permuted.

n_prob_schedule:int, default=30
  The number of steps used to decrease the prob parameters.
        if i in np.arange(num_steps/10, num_steps, step=num_steps/n_prob_schedule):
          prob *= 0.9
          
temperature:int, default=None
  The value of the temperature in the Simulated Annealing strategy.
  If set to None, no Simulated Annealing

plot:Bool, default=False
  If set to true allow to plot thr graph of the evolution of Fitness Function,
  togheter with information about the initial state and final state (validity and cost value).
  Time of execution is also printed, in seconds.


