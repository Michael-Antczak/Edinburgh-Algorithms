# Insertion sort

A method for sorting that starts with a single element (thus forming a trivially sorted list) and then incrementally 
inserts the remaining elements so that the list stays sorted.

```C
insertion_sort(item s[], int n)
{
  int i, j;     /* counters */
  
  for (i = 1; i < n; i++) {
    j = i;
    
    while ((j > 0) && (s[j] < s[j-1])) {
      swap(&s[j], &s[j-1]);
      j = j - 1;
    }
  }
}
```

```
InsertionSort(A)
  A[0] = −∞
  for i = 2 to n do
    j = i
    while (A[j] < A[j − 1]) do
      swap(A[j], A[j − 1])
      j = j − 1
```
