# Selection Sort

## Sorting Problem
We have a list of data to be sorted.
- list simply refers to a sequential container type
- the actual data type does not matter
- e.g. Static Array, List, Linked List
We have a comparison operator `R` that defines a linear order of elements
- for two elements `a!=b`, `aRb` or `bRa` must hold true, not both
- e.g. operator `<`: if `a!=b`, then either `a<b` or `b<a`, not both

Example:
- we have: `5, 3, 2, 4, 1`
- operator: `>`
- result: `5, 4, 3, 2, 1`

## Selection Sort
Let's start with an example right away. Probably the most intuitive one:
- find the smallest element in the list
- swap the smallest element with the first
- continue the previous steps for the remaining list until the list is empty

<img width="299" alt="image" src="https://user-images.githubusercontent.com/7360266/150952165-82dba5e0-bf8f-4552-b0fc-b19c7960c2cd.png">

<details>
  <summary>Pseudo-Code</summary>
  
  ```
procedure selection sort 
   list  : array of items
   n     : size of list

   for i = 0 to n - 2
     /* set current element as minimum */
      min = i    
  
      /* check the element to be minimum */

      for j = i + 1 to n - 1
         if list[j] < list[min] then
            min = j;
         end if
      end for

      /* swap the minimum element with the current element */
      if min != i  then
         swap list[min] and list[i]
      end if
   end for
	
end procedure
```

</details>

Is this a good algorithm?

## Classifying Algorithms

Many algorithms work with a variable size of data. 10, 100, 1000, 1000000, ...

How can we classify algorithms in terms of efficiency?

### Time Factor
- How much time does it take from start till end?
### Space Factor
- How much memory does it consume?
### Fluctuation
- Both have Min, Max and Average values.
- Also called Best Case, Worst Case and Average Case Scenarios.
### Complexity
Both Time and Space Factor can be split into two parts:
- Constant Part. Stays the same, no matter the size of the problem.
  - e.g. a `for` loop always needs **one** `int`. No matter the size.
- Variable Part. It scales with the size of the problem.
  - e.g. some sorting algorithms need a second array, same size as the array to be sorted.

This field is called:
> Asymptotic Analysis

### Greediness

Imagine the following problem: We need to write an algorithm that hands out coins to the customer. The type of coins are 1,2,5,10.

A greedy algorithm would always return the largest coin first. Example: 23:
- Give: 10, Remaining: 13
- Give: 10, Remaining 3
- Give: 2, Remaining: 1
- Give: 1, Remaining: 0

Result: 10, 10, 2, 1

=> Does this Algorithm work for any amount of money given?

What, if thee type of coins were 1, 7, 10?

Example: 15:
- Give: 10, Remaining: 5
- Give: 1, Remaining: 4
- Give: 1, Remaining: 3
- Give: 1, Remaining: 2
- Give: 1, Remaining: 1
- Give: 1, Remaining: 0

Result: 10, 1, 1, 1, 1, 1

Wouldn't 7, 7, 1 be the best result?

This is, why it's called a greedy algorithm. It always tries to go for the most obvious solution first. The one, that brings us to the goal more efficiently. Through that, it might discard the best solution, though.

<img width="652" alt="image" src="https://user-images.githubusercontent.com/7360266/150950573-ad4bbd70-d1d1-46f8-8796-45fec0a2c38e.png">


This is called the difference between a Local and Global Optimum. Greedy Algorithms fall into a trap of a Local Optimum, where a solution seems to be the best given a limited field of vision, but there might be a Global Optimum that's even better.

Analogy: You want to visit a friend next town and you wonder how to get there efficiently. You check a few options and notice that taking the bike will greatly speed you up and get you there much more quickly on a small forest route that leads there almost directly. But you forget to consider walking the opposite way to the train station, which will bring you there much faster.

Are greedy algorithms bad? No, they're essential! Algorithms that are not greedy often need to analyze every possible combination of a problem. In chess, that number is somewhere around 
> 999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999 possible moves. 

That's 10^110. In comparison, the amount of atoms in the observable universe is only estimated at 10^80. 

To be fair, the amount of typical chess moves is "only" around 10^40.

But anyways, that number of possible combinations is literally impossible to calculate. Even 1 Million people on 1 Million Earths in 1 Million Galaxies, each using 1 Million Computers and looking at 1 Million states per second would still need 10^72 years. In comparison, the age of the universe is only 10^9 years. Just to give you some idea of what complexity we're talking about here. So, sometimes, greed is good after all :D

### Stability
Some sorting algorithms maintain the order of items of the same value, while others don't.

e.g. imagine an algorithm that only sorts by the first digit:
- given: `7A, 5B, 5A`
- operator: `<`
- output: `5B, 5A, 7A`

Here, the order of both items with digit `5` has been maintained. This would be called a stable sorting algorithm.

Some algorithms might end up with:
- output: `5A, 5B, 7A`

Here, the order of items with the "same" value has changed. This would be called an unstable sorting algorithm.

### In-Place
In Sorting Algorithms, for them to be called In-Place, the Variable Part of the Space Complexity should be 0. As in, the algorithm should not consume Memory relative to the size of the collection. This can be very important for large collections.

Remember the software crashing when calculating the sum of 1.000.000.000 Numbers when they were an array?

Opposite: Out-of-place sorting algorithm.

## Classifying Selection Sort
### Unstable
- consider: 133234
- stable implementation is possible, but at extra costs (how?)
### In-place
- memory required only for loop counter `i` and swap space for one element. The swap space can be avoided, but at extra costs (how?)
### Complexity
- For `n` elements:
- Swap Operations (worst case): `n-1`
- Compare operations:
  - (n-1) + (n-2) + ... + 2 + 1
  - (n^2)/2 - n/2
  - O(n^2)