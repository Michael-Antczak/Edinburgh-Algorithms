# Compare sorting efficiency
and why computer power does not matter that much...   

What we care about is to have a way to compare the algorithms independent of the computer they run on. We need to link the **size of the input** and the **change in the running time**. We are interested in the **order of magnitude**, i.e. what is the change in the running time when I double the input?     

## How do we evaluate algoritms?

  The running time of a program depends on a number of factors such as:
  - The input given to the program ([input size example](https://github.com/Michael-Antczak/Intro-to-computer-science/tree/master/examples/size_of_input))
  - The running time of the algorithm on which the program is based.  
  - The quality of the implementation and the quality of the code generated by
the compiler 
  - The machine used to execute the program  

## Problem:
sort an array of 10 million numbers **(10<sup>7</sup>)**

#### Faster computer (computer A) 
- running insertion sort - **O(n<sup>2</sup>)**
- executes 10 billion instructions per second - **10<sup>10</sup>** 
- suppose that the world’s craftiest programmer codes insertion sort in machine language for computer A, and the resulting code
requires **2n<sup>2</sup>** instructions to sort n numbers

#### Slower computer (computer B) 
- running merge sort - **O(nlgn)**
- executes only 10 million instructions per second - **10<sup>7</sup>** (so A is 1000 times faster than computer B in raw computing power)
- suppose further that just an average programmer implements merge sort, using a high-level language with an inefficient
compiler, with the resulting code taking **50nlgn** instructions.

So the equation for the running time of the **computer A** would be:

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{150}&space;\large&space;\frac{2*(10^{7})^{2}}{10^{10}}=&space;20,000sec&space;\approx&space;5.5hrs" target="_blank"><img src="https://latex.codecogs.com/png.latex?\dpi{150}&space;\large&space;\frac{2*(10^{7})^{2}}{10^{10}}=&space;20,000sec&space;\approx&space;5.5hrs" title="\large \frac{2*(10^{7})^{2}}{10^{10}}= 20,000sec \approx 5.5hrs" /></a>

and for the **computer B**:  

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{150}&space;\large&space;\frac{50*10^{7}lg10^{7}}{10^{7}}=&space;1,163sec&space;\approx&space;20mins." target="_blank"><img src="https://latex.codecogs.com/png.latex?\dpi{150}&space;\large&space;\frac{50*10^{7}lg10^{7}}{10^{7}}=&space;1,163sec&space;\approx&space;20mins." title="\large \frac{50*10^{7}lg10^{7}}{10^{7}}= 1,163sec \approx 20mins." /></a>

#### Algorithms matter!

## Exercise
What is the smallest value of **n** such that an algorithm whose running time is **100n<sup>2</sup>** runs faster than an algorithm whose running time is **2<sup>n</sup>** on the same machine?

| Algorithm and n | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 10 | 12 | 14 | 15 | 16 | 17 |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| 100n<sup>2</sup>  | 100 | 400 | 900 | 1600 | 2500 | 3600 | 4900 | 6400 | 10,000 | 14,400 | 19,600 | 22,500 | 25,600 | 28,900 | 
| 2<sup>n</sup>  | 2 | 4 | 8 | 16 | 32 | 64 |128 | 256 | 1024 | 4096 |16,384 | 32,768 |65,536 | 131,072 |
