# Genetic Algorithm Timetable Optimization

## Project Overview

This project implements a Genetic Algorithm (GA) to optimize the scheduling of university timetables. The algorithm works by generating and evolving timetables, ensuring minimal conflicts between course assignments, room allocations, and professor availability. The system accounts for various constraints, both hard (e.g., room capacity, professor course load) and soft (e.g., minimizing room changes or time slot preferences).

## Features

-   **Population-based optimization**: The algorithm starts with a random population of timetables and evolves them over multiple generations.
-   **Conflict management**: The system penalizes conflicts such as professor over-assignments, section overlaps, room double bookings, and room capacity issues.
-   **Crossover and mutation**: Utilizes genetic operators like crossover and mutation to explore the solution space and improve the timetable generation.
-   **Adaptive penalty adjustment**: Increases penalties dynamically for conflicts to guide the solution towards better timetables.
-   **Timetable repair**: Adjusts lectures and resolves room conflicts during the optimization process to improve feasibility.
-   **Scalable**: Can handle multiple classes, rooms, and sections while efficiently managing constraints.

## Installation

1.  Clone the repository.
2.  Install the necessary dependencies:
    
    bash
    
    Copy code
    
    `pip install numpy` 
    
3.  Run the genetic algorithm notebook:
    

    
    `python timetable_optimization.ipynb` 
    

## How It Works

1.  **Initial Population**: A set of random timetables is generated as the initial population.
2.  **Evaluation**: Each timetable is decoded and evaluated based on the number of conflicts it generates, such as double-booking rooms or assigning a professor too many courses.
3.  **Selection**: The best timetables are selected based on their fitness scores (fewer conflicts).
4.  **Crossover**: Selected timetables are combined to create new solutions by swapping parts of their structure.
5.  **Mutation**: A small percentage of timetables undergo random changes to introduce diversity into the population.
6.  **Repair**: If conflicts like room double-bookings occur, the timetable is repaired to improve feasibility.
7.  **Adaptive Penalty Adjustment**: Penalties for conflicts increase dynamically during the optimization process to push the algorithm toward better solutions.

## Parameters

-   **n_bits**: Number of bits used to encode each timetable.
-   **n_pop**: Population size.
-   **r_cross**: Crossover rate.
-   **r_mut**: Mutation rate.
-   **n_classes**: Number of classes.
-   **n_rooms**: Number of rooms.

## Example Output

The program will output the best timetable and display its conflicts:

yaml

Copy code

`Optimization completed.
Best solution: <bitstring representation>
Best fitness score: 0.00234
Total Conflicts: 3` 

The decoded timetable will list details such as course assignments, room allocations, and the timeslot for each lecture.

## Contributions

Feel free to submit issues, feature requests, or pull requests.
