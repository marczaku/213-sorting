# Evaluation of Algorithms

## Big O Notation
The Big-O Notation looks at the upper bound of a function. Common complexities are:

<img width="98" alt="image" src="https://user-images.githubusercontent.com/7360266/151051143-ed284542-baf8-4e84-81f4-950571754efd.png">

O(1) - constant
- behavior does not depend on size

<img width="95" alt="image" src="https://user-images.githubusercontent.com/7360266/151051214-82d5d43b-139a-4038-8b20-7db2fc1eeed9.png">

O(log n) - logarithmic
- grows by constant factor when problem size doubles
- base of the logarithm does not matter (it barely does)

<img width="92" alt="image" src="https://user-images.githubusercontent.com/7360266/151051318-3e9928ae-e2dd-4ea7-8255-b8b7745b9915.png">

O(n) - linear
- resources grow linearly with size
- i.e. size doubles -> resources double

<img width="96" alt="image" src="https://user-images.githubusercontent.com/7360266/151051370-497a6470-9aa9-45b7-8196-09420f5a407f.png">

O(n log n) - linear-logarithmic
- more disadvantageous than logarithmic, but better than linear for large size

<img width="94" alt="image" src="https://user-images.githubusercontent.com/7360266/151051422-ef778f14-df56-46ae-ba8a-7510e7e474dc.png">

O(n^2) - quadratic
- grows 4x when size doubles

<img width="94" alt="image" src="https://user-images.githubusercontent.com/7360266/151051512-650d4f3e-2b02-4a5e-9190-f2727b2141fb.png">

O(2^n) - exponential
- grows 2x when size increases by 1

## Evaluation of Sorting Algorithms
Like most things in programming, there's no clear winner. You can look at:

- the memory requirements. Can you afford extra memory consumption? This can give you speed gains.

- the time behavior of the algorithm
  - number of comparisons
  - number of swaps
  - depending on problem size

Which one is more expensive? Comparison or Swaps?

=> Depends on your data!

## Special cases
How does an Algorithm behave
- in best case?
- in worst case? (and how likely is that?)
- the average case?

What if the list
- is already sorted?
- almost sorted? 
- sorted in reverse order?