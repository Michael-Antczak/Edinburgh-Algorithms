# Shell sort
otherwise known as *diminishing increment sort*

## Outline
1. Problem
1. Invention
1. High level overview
1. Example
1. Pseudocode

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

# Pseudocode

Version 1

```python
# Sort an array a[0...n-1].
gaps = [701, 301, 132, 57, 23, 10, 4, 1]

# Start with the largest gap and work down to a gap of 1
foreach (gap in gaps)
{
    # Do a gapped insertion sort for this gap size.
    # The first gap elements a[0..gap-1] are already in gapped order
    # keep adding one more element until the entire array is gap sorted
    for (i = gap; i < n; i += 1)
    {
        # add a[i] to the elements that have been gap sorted
        # save a[i] in temp and make a hole at position i
        temp = a[i]
        # shift earlier gap-sorted elements up until the correct location for a[i] is found
        for (j = i; j >= gap and a[j - gap] > temp; j -= gap)
        {
            a[j] = a[j - gap]
        }
        # put temp (the original a[i]) in its correct location
        a[j] = temp
    }
}
```

Version 2
```C
input a array

N = a.length
int h = 1

while (h < N/3) h = 3 * h + 1     //  1, 4, 13, 40, 121, 364, ....

while (h >= 1) 
  {   // h-sort the array
    
      for (int i = h; i < N; i++) 
        {    // insert a[i] among a[i-h], a[i-2*h], a[i-3*h], ...
        
            for (int j = i ; j >= h && less(a[j], a[j-h]) ; j -= h)
            
                exch(a, j, j-h)
            
        }
        
        h = h / 3
    
  }
  

```

# Resources
1. Original paper:   [A High-Speed Sorting Procedure](http://penguin.ewu.edu/cscd300/Topic/AdvSorting/p30-shell.pdf) by [Donald L. Shell](https://en.wikipedia.org/wiki/Donald_Shell)
