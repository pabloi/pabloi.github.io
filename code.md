---
layout: page
title: code
permalink: /code/
---

These are some of my coding projects. Most of it was  during my PhD work at Pitt's [Sensorimotor Learning Lab](http://www.engineering.pitt.edu/Sub-Sites/Labs/SML_Lab/_Content/Home/Homepage/), and are coded for Matlab (although I am now coding mostly in Python).

## matlab-linsys
Linear dynamic systems toolbox for Matlab. Includes tools for identification (EM and subspace methods), selection (BIC, AIC, cross-validation), visualization, and comparison of linear systems.
It implements the Kalman filter and Kalman smoother (in covariance, information and square root formulations), with emphasis on filtering speed.
Offers an object-oriented wrapper of most of its functionality to facilitate its adoption.
[Repository](www.github.com/pabloi/matlab-linsys)

## monoLS
Data smoothing through monotonic curve fitting for Matlab and Octave.  
MonoLS finds the optimal monotonic (i.e. non-negative or non-positive derivative) curve fit to some dataset of (x,y) points. Higher-order derivatives can also be constrained to be of constant sign (or 0), but the same sign has to be used for all odd-order derivatives and for all even-order derivatives. A regularization term is used to avoid undue deference to datapoints near the extremes of the x range. By default, monoLS uses mean-squared errors so it is the least-square solution. In this case, the problem can be framed as a non-negative least squares problem (which is always convex).
[Repository](www.github.com/pabloi/monoLS)

## robustCov
A simple, fast, heuristic, robust covariance matrix estimator to deal with data with outliers (MatlaB). 
[Repository](www.github.com/pabloi/robustCov)

## pi-tools
Collection of Matlab utilities to make my life easier. Includes functions for visualization, non-parametric statistical tests, and filtering.
[Repository](www.github.com/pabloi/pi-Tools)

## labTools
A suite of Matlab utilities to load, clean, process, visualize and analize experimental gait data. Used in all past and present studies by Pitt's [Sensorimotor Learning Lab](http://www.engineering.pitt.edu/Sub-Sites/Labs/SML_Lab/_Content/Home/Homepage/).
Experimental data is organized and stored in custom-made hierarchical object-oriented structures, and most functionality is implemented as class-specific methods for these objects.
[Repository](www.github.com/PittSMLLab/labTools)

## HMRLHardware
Interfacing functions to communicate with Pitt SML Lab's (formerly HMRL) hardware and software from Matlab to have a single point of control for experiments. Hardware includes a Bertec split-belt treadmill, and software includes Vicon's Nexus.
[Repository](www.github.com/pittsmllab/HMRLhardware)

## splitbelt-EMG-adaptation
Data and code (Matlab) for the research project published in [Corrective Muscle Activity Reveals Subject-Specific Sensorimotor Recalibration](https://www.eneuro.org/content/6/2/ENEURO.0358-18.2019)
[Repository](www.github.com/PittSMLlab/splitbelt-EMG-adaptation)


## Some tools that I like to use in my work
- <i class="ai ai-overleaf" style="color:gray"></i> [Overleaf](http://www.overleaf.com)
- <i class="ai ai-mendeley" style="color:gray"></i> [Mendeley](http://www.mendeley.com)
- <i class="ai ai-figshare" style="color:gray"></i> [FigShare](http://www.figshare.org)
- [GitKraken](http://www.gitkraken.com)
- [Atom](http://www.atom.io)
- [GitHub](https://www.github.io)
