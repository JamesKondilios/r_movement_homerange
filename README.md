# r_movement_homerange

#### collection of animal movement and utilization distribution scripts in R

**[trajectory_info.r](https://github.com/dnbucklin/r_movement_homerange/blob/master/trajectory_info.r)**

This script takes input locations in a text file and returns a point shapefile with information about each point in the trajectory (angles, distance to next point, etc.)

**[site_fidelity_test.r](https://github.com/dnbucklin/r_movement_homerange/blob/master/site_fidelity_test.r)**

This script compares animal movement trajectories to a set of randomly generated trajectories (generated by randomizing the true trajectories' steps' angles and distances. It compares the true trajectories' R-squared and linearity value to the distribution of R-squared and linearity values of the random replicates, following a procedure implemented in the Site Fidelity tool of Animal Movement Extension for ArcView (http://alaska.usgs.gov/science/biology/spatial/gistools/animalmovementdoca.pdf).

It takes inputs of animal locations and a shapefile with one polygon which represents the area available to the animal (this constrains the random walks). Plots are output displaying the trajectory and random walks, and a output table with r-squared, linearity, and p-values for each track.

####Home range estimators

Note: these tools can be accessed in a shiny web-app [here](https://dbshiny.shinyapps.io/hr_explorer).

**[mcp_and_kde.r](https://github.com/dnbucklin/r_movement_homerange/blob/master/mcp_and_kde.r)**

This script creates 2 types of utilization distribution estimations from point locations, minimum convex polygon (also know as convex hull) and kernel density estimation. It uses mainly functions from the adehabitatHR package, with some customization to allow for rescaling of locations prior to kernel density estimation, replicating the option in the Kernel Density Estimation tool in the Home Range Tools extension developed for ArcView and ArcGIS 9 (http://flash.lakeheadu.ca/~arodgers/hre/); see the HRT manual [here](http://flash.lakeheadu.ca/~arodgers/hre/HRT%20Users%20Manual%20Draft%20August%2010%202011.pdf).

The script requires a specific input file containing animal ID, track ID, date, time, and X/Y coordinates. It outputs a summary of the run and shapefiles for each utilization distribution.

**[triangulated_utildists.r](https://github.com/dnbucklin/r_movement_homerange/blob/master/triangulated_utildists.r)**

Experimental - utilization distributions based off of Delaunay triangulations. Requires alpha-functions.r script in working directory.

**[alpha-functions.r](https://github.com/dnbucklin/r_movement_homerange/blob/master/alpha-functions.r)**

Required functions for triangulated_utildists.r - for converting alpha shapes into spatial lines data frames.
