---
layout: post
title:      "Finding my Path, through ALGORITHMS"
date:       2019-12-28 16:17:51 +0000
permalink:  finding_my_path_through_algorithms
---


I recently watched a youtube video by Clément Mihailescu on the topic of Pathfinding algorithms, and I have been fascinated by them ever since. His video was a tutorial on how to create a pathfinding visualization software which I followed along with, and had a lot of fun playing around with afterwards. In the video he demonstrates how to create a visualization of Dijkstra's algorithm, which in this case finds the shortest path by assigning an integer value to nearby nodes to a starting node, and upon reaching the finish node, determines the shortest path based on those integer values. It essentially searches every single possible route until it reaches the finish. Though this was able to complete the simple goal of finding the shortest path to the destination, what if we wanted to find something faster?

In the video, the A* algorithm was mentioned and upon doing a little bit of research I found that it is just a generalized version of Dijkstra's algorithm, that functions similarly however it has the added benefit of a "guess" which allows the algorithm to reach the goal in less time. This "guess" is known as a heuristic, which is used to construct a function of the cost it would take you to reach the destination. This function, f(n) (where n is a particular node), is defined as f(n) = g(n) + h(n), where g(n) is the known amount, or aggregate distance already travelled, and h(n) is the heuristic function being used. A* takes the cake in terms of speed towards a destination provided your heuristic function doesn't overestimate the cost of reaching the goal. This prompted me to work on a project which served to compare the A* and Dijkstra's algorithms.

The project itself is an identical clone to Mihailescu's as of right now, however I added a button which will utilize A* to find the optimal path in order to add my own spin on things. Though this is only my introduction to pathfinding, I look forward to the challenge that it provides!
