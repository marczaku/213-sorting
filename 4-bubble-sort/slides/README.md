# Bubble Sort
- extremely naive sorting algorithm
  - mostly used as a bad example


- compares two neighboring elements
- swaps them if necessary
- does this for the whole list
- repeats above steps until no more swaps happen in one run

<img width="525" alt="image" src="https://user-images.githubusercontent.com/7360266/150951649-dc813f7d-43f3-475e-8751-d0c085571750.png">

<details>
  <summary>Pseudo-Code</summary>

```
procedure bubbleSort( list : array of items )

   loop = list.count;
   
   for i = 0 to loop-1 do:
      swapped = false
		
      for j = 0 to loop-1 do:
      
         /* compare the adjacent elements */   
         if list[j] > list[j+1] then
            /* swap them */
            swap( list[j], list[j+1] )		 
            swapped = true
         end if
         
      end for
      
      /*if no number was swapped that means 
      array is sorted now, break the loop.*/
      
      if(not swapped) then
         break
      end if
      
   end for
   
end procedure return list
```

</details>

## Optimization:
- largest element is guaranteed to be at the correct position after first pass
- can decrement sorting area size after every pass

## Classifying Bubble Sort
### Stable
- better than Selectionsort
### In-place
- similar to Selectionsort
### Complexity
- For `n` elements:
- Swap Operations (worst case): 
  - 0.5*(n^2-n)
  - O(n^2)
  - worse than Selectionsort, which had O(n)

- Compare operations (worst case):
  - same as swap operations
  - same as Selectionsort

- BUT optimal best case!
- Much better than Selectionsort. How much?