---
layout: post
title:      "Python Classical Mechanics"
date:       2020-01-19 17:37:17 +0000
permalink:  python_classical_mechanics
---

In my eternal quest to find new ways to view physics simulations I found a blog on cyber-omelette (linked below), by Ben Eagen which details the basics of Newtonian gravity, and how to plot a simple solar system in python. In his article, Eagen does an incredible job of breaking down the basics of the classical interpretation of gravity, a radial force that pulls two massive bodies together. His code utilizes the Euler method of approximation, which calculates the position of the planets in the solar system by examining the simultaneous changes of position of each of the bodies with incredibly small steps in time, and the resultant acceleration due to gravity, in order to attain an accurate orbital path.

This idea of simulating physical systems has been fascinating to me since beginning my undergradate degree, and after seeing some of the basic capabilities of Python, I decided to use the Euler method to simulate two dimensional projectile motion.  I began by using the vpython library to construct a ball with a reasonable radius, a surface that the ball will eventually reach which is given a y value of zero, and an initial surface that the ball would be launched from. The ball is given an initial velocity, whose components are used to construct the velocity vector of the ball, and an initial angle used to calculate those velocity components. In order to insure that the Euler approximation was accurate, a very small change in time, represented by the variable dt was assigned to be 0.001s. Though the only surface in our approximation was the "table" floating in the vacuum of space, and the "ground" similarly floating in space, I used the constant g=-9.81m/s^2 to simulate earth-like conditions. From here we could begin taking measurements of the velocity and position of the ball for every dt, in a while loop until the y coordinate of the position of the ball becomes zero. Once this position is reached, we are able to output the distance traveled, and the time it took to travel that distance. 


Though this is still a simple system, I hope to continue to use code to interpret and visualize the physical world, in an attempt to make complex systems more palettable. A big thank you to Ben Eagen for inspiring this code, and for giving the world more "recreational physics"!



## Resources
[http://www.cyber-omelette.com/2016/11/python-n-body-orbital-simulation.html](http://)

