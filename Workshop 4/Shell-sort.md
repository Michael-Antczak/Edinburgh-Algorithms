# Shell sort
otherwise known as *diminishing increment sort*

## Outline
1. Problem
1. Invention
1. High level overview
1. Example

# Problem

If we are looking for quick algorithms, usually we choose mergesort or quicksort. The problem may be when we have a limited memory. 

Mergesort - memory **O(n)**  
Quicksort - memory from **O(lgn)** to **O(n)**   

The problem with selection and insertion sort is that in the worst case scenario, the lower values are at the back and they not "travel" to the front very quickly.  

So the idea here is to have a quick sorting algorithm (at least quicker then insertion, selection and bubble sort) and at the same time using as little memory as possible.  

# Invention

It was invented in 1959 by [Donald Shell](https://en.wikipedia.org/wiki/Donald_Shell)

# High level overview

The idea: 
* longer leaps - increase the gap between items being exchanged (why small gaps is a problem?)
* least memory footprint
* move lower items from the end to the front quicker
* use other sorting algorithm for the subarrays (smaller size, partially sorted so suitable for other n^2 algorithms - insertion)

So how it works: 


# Example

1. Let's start with the following sequence:   **6** **5** **4** **3** **2** **1**

1. Now something a wee bit longer: 

# Resources
1. Original paper:   [A High-Speed Sorting Procedure](http://penguin.ewu.edu/cscd300/Topic/AdvSorting/p30-shell.pdf) by [Donald L. Shell](https://en.wikipedia.org/wiki/Donald_Shell)
