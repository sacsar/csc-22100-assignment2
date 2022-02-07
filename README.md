# CSc 22100 Spring 2022 Assigment 2

In this assignment, we'll implement a simulation of 1-dimensional [elementary cellular automata](https://mathworld.wolfram.com/ElementaryCellularAutomaton.html).

From [Mathworld](https://mathworld.wolfram.com/CellularAutomaton.html):

> A cellular automaton is a collection of "colored" cells on a grid of specified shape that evolves through a number of discrete time steps according to a set of rules based on the states of neighboring cells. The rules are then applied iteratively for as many time steps as desired. von Neumann was one of the first people to consider such a model, and incorporated a cellular model into his "universal constructor."

Elementary cellular automata are cellular automata with a single dimension where:
- each cell has only two possible values (on/off, 1/0, black/white)
- the next state of a cell is determined solely by its state together with the states of its left and right neighbors.

There are 8 (2x2x2) possible states for a cell and its two neigbors. To define an elementary cellular automaton, for each of these eight states, we need to decide if the center cell is on or off in the next generation. This means there are 2^8=256 possible rules defining cellular automata.

Each number from 0 to 255 can then be interpreted as a _Wolfram code_ defining a cellular automaton. We start by writing down the eight possible states for a cell and its neighbors (the order matters!).

| 111 | 110 | 101 | 100 | 011 | 010 | 001 | 000 |

Next, we take our integer and translate it into binary. For example, suppose we want to determine the transition rule for automaton 37. 37 in base 2 is 100101. We pad the base 2 representation with 0s until we have eight digits: 00100101. Then, line up each of these digits under the eight states. This gives us the following transition rules:

![Rule 37](./rule37.png)

## Requirements

Resources:
- [1D ECA Simulator](https://elife-asu.github.io/wss-modules/modules/1-1d-cellular-automata/) (warning: this site displays the correct transitions, but in a non-standard order)


