# Two-body problem using RK2 and RK3

This repository contains an implementation of Runge-Kutta of second and third order solvers for the two-body problem between the Earth and Sun using either RK2 or RK3

The script is written in Python and consists of the following files:

## 1) kepler.py

This file contains the main code for solving the two-body problem between the Earth and Sun using either RK2 or RK3. The code uses the argparse library to set the parameters for each simulation.

The code has been written in Python and requires the following packages to be installed:

    numpy
    matplotlib
    os
    glob
    PIL
    argparse

### Usage

The solver can be run in the terminal where the folder is located following command:
    
    python kepler.py -im -g -RK <order of the RK (2 or 3)> -T <number of periods> -e <eccentricity value> -k <step_sizes> .

where 

    including -im allowsto save the initial map,  
    including -g returns a GIF animation containing the Earth position and velocity at different times.
    <order of the RK (2 or 3)>  allows to select the Runge-Kutta of second or third order. Must be integer values 2 or 3.
    <number of periods> states the total number of periods of earth. Must be an integer value.
    <eccentricity value> must be an floating value.
    <eccentricity value> must be an floating value.
    <step_sizes> must be the step sizes using in the RK method

For example, if we want a simulation for eccentricity e=0.01671 for T=5 periods using RK2 with step sizes of 0.01 and saving the initial map and the GIF animatio,n we must run as follow: 

    python kepler.py -im -g -RK 2 -T 5 -e 0.01671 -k <0.01>.

## 2) outputs
        
The outputs of the code are saved in the outputfolder in a directory named Period_<T>-ecc_<e>-t_step_<k>, which is created if it does not exist. 
These include a:
        
        - history.txt that saves the history of the Earth's orbital motion
        - a directory called orbits_images with the simulation images for each time step 
        - and if its desired, the intial map and the GIF animation.

## 3) analysis.ipynb

This Notebook contains the answer for the part g and h of the exam. 

It generates the file compared_orbtits.gif in the output folder which compare the orbits history using e=0.25 (Pluto's eccentricity) and e=0.01671.

Also, it measure the convergence of RK3 by calculating the radius error after one period for different step sizes used.


