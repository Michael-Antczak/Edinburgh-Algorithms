# Compare sorting efficiency

### Problem:
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
