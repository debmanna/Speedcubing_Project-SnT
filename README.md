# Speedcubing_Project-SnT
This project was offered by the Speedcubing Club, IIT Kanpur under the Science and Technology Council during  2020-21-II Semester. The Solver part focused on solving a random scramble of a 3x3 cube using the [Thistlethwaite method](https://www.speedsolving.com/wiki/index.php/Thistlethwaite%27s_algorithm).

## [Solver Part Assignments](./Assignments)

We were given some assignments to get comfortable with basics of cube theory, cube notations, STL in C++ and graphs. This folder contains my personal submissions.

### [Assignment 1](./Assignments/Assignment-Cube_Theory.pdf)

It was based on [Cube Theory](https://drive.google.com/file/d/1-L8xNXRVEk7S3XBuYOkQsc3FINxan_kR/view). We were provided with resources ([Basic Notations]( https://www.youtube.com/watch?v=24eHm4ri8WM)) to get familiar with it. Answers were collected through a Google form.

### [Assignment 2](https://drive.google.com/file/d/1XwmhHPa-5fvditAgEnfbNlL2H7o9env8/view?usp=sharing)

We had to learn about [C++ STL](https://www.topcoder.com/thrive/articles/Power%20up%20C++%20with%20the%20Standard%20Template%20Library%20Part%20One) and [Graphs](https://drive.google.com/drive/folders/1qQd7vYsYINyJXW3aAHLy3GQ-X2Ykwsfj?usp=sharing).
The submission to assignment can be found as [P1Q1](./Assignments/P1Q1.cpp), [P1Q2](./Assignments/P1Q2.cpp), [P1Q3](./Assignments/P1Q3.cpp), [P1Q4](./Assignments/P1Q4.cpp), [P2Q1](./Assignments/P2Q1.docx), [P2Q2](./Assignments/P2Q2.docx), [P2Q3](./Assignments/P2Q3.docx) and [P2Q4](./Assignments/P2Q4.docx).

### [Assignment 3](https://drive.google.com/file/d/184hLinhG3RXp9sCip5-nHKNuxxzBZ6Q8/view?usp=sharing)

We had to implement the [Double Ended BFS](https://efficientcodeblog.wordpress.com/2017/12/13/bidirectional-search-two-end-bfs/
) to perform the sequence of moves to finish a Phase in the Thistlethwaite method. This was a sub task for the code [SolverCodeThistlethwaite.cpp](./Solver_Simulator_Integration/SolverCodeThistlethwaite.cpp).





## [Solver Simulator Integration](./Solver_Simulator_Integration)

### Aims:

-Integrating the Solver code (Thistlethwaite method) with the 3x3 Simulation.

-Collecting data after performing random scrambles and feeding it to the Solver code.

-Getting statistics

#### 1. Integration:

We used text files to communicate with the two different codes (one in C++ and other in Processing).

The simulator code was modified so that it returns the moves we randomly perform into a text file [RandomScramble.txt](./Solver_Simulator_Integration/RandomScramble.txt). This file now acts as an input for our Solver code.

The Solver code ([SolverCodeThistlethwaite.cpp](./Solver_Simulator_Integration/SolverCodeThistlethwaite.cpp)) takes the inputs from [RandomScramble.txt](./Solver_Simulator_Integration/RandomScramble.txt) and after applying phase wise double-ended BFS, it returns a sequence of moves that will solve the cube. This sequence of moves is written to a file called [SolverOutput.txt](./Solver_Simulator_Integration/SolverOutput.txt). Basically, running the Solver code on a C++ compiler will automatically take the input and create the output file for you!

Now the simulator code reads the sequence of moves from [SolverOutput.txt](./Solver_Simulator_Integration/SolverOutput.txt) and performs those moves on the cube.



#### 2. Collecting Data:

The Solver code was modified to [DataGenerator.cpp](./Solver_Simulator_Integration/DataGenerator.cpp)  in order to get data about phase wise moves, the time taken for each phase in addition to the total moves and total time taken.

A sample of random scrambles was taken as a text file ([RandomScrambleData.txt](./Solver_Simulator_Integration/RandomScrambleData.txt)) and was passed on to [DataGenerator.cpp](./Solver_Simulator_Integration/DataGenerator.cpp). It generated the required data into a text file ([Data.txt](./Solver_Simulator_Integration/Data.txt)). This data will now be used to generate statistics.



#### 3. Statistics:

The text file [Data.txt](./Solver_Simulator_Integration/Data.txt) was converted to `.csv` format contained in [Data__Stats.xlsx](./Solver_Simulator_Integration/Data__Stats.xlsx). Then carried out basic statistical operations on the csv file in MS Excel. `Sheet 1` of [Data__Stats.slsx](./Solver_Simulator_Integration/Data__Stats.xlsx) contains the data (and some theoretical stats) whereas `Sheet 2` has the stats represented graphically.

The [Converter.py](./Solver_Simulator_Integration/Converter.py) contains the code to convert the `.txt` file generated by the solver code to `.csv` file.



### Team Members:
- Mandar Wayal
- Debanjan Manna
- Narendra Prajapat

