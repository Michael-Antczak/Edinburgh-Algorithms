# Selection sort


```c
selection_sort(int s[], int n)
  {
  int i,j; /* counters */
  int min; /* index of minimum */
  for (i=0; i<n; i++) {
    min=i;
    for (j=i+1; j<n; j++)
      if (s[j] < s[min]) min=j;
      swap(&s[i],&s[min]);
  }
  }
```

```javascript
/* a[0] to a[n-1] is the array to be sorted */
int i,j;
int n;

/* advance the position through the entire array */
/*   (could do j < n-1 because single element is also min element) */
for (j = 0; j < n-1; j++) 
  {
    /* find the min element in the unsorted a[j .. n-1] */

    /* assume the min is the first element */
    int iMin = j;
    /* test against elements after j to find the smallest */
    for (i = j+1; i < n; i++) {
        /* if this element is less, then it is the new minimum */
        if (a[i] < a[iMin]) {
            /* found new minimum; remember its index */
            iMin = i;
        }
    }

    if(iMin != j) 
    {
        swap(a[j], a[iMin]);
    }
}
```
