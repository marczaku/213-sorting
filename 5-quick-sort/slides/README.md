# Quicksort
- very fast algorithm

Idea:
- divide and conquer
- split the problem in half
- solve each half independently
- combine the results
- can split as often as necessary

<img width="626" alt="image" src="https://user-images.githubusercontent.com/7360266/150951414-d539f23f-a025-486b-a123-3a4ffccda763.png">

<details>
  <summary>Pseudo-Code</summary>

```
procedure quicksort(list, low, high)
    if low <= high then
        partitionIndex := partition(list, low, high)
        quicksort(list, low, partitionIndex - 1)
        quicksort(list, partitionIndex + 1, high)
    end if
end procedure

procedure partition(list, low, high)
    pivotValue := list[high] // could be replaced by alternative pivot selection methods
    partitionIndex := low
    for j := partitionIndex to high - 1 do
        if list[j] < pivotValue then
            swap list[partitionIndex] with list[j]
            partitionIndex++
        end if
    end for
    swap list[partitionIndex] with list[high]
    return partitionIndex
end procedure
```

</details>

## Classification
- unstable: elements with same value do not maintain relative order to each other
- inplace: we do not allocate additional memory
  - but: it is a recursive function, so it requires stack memory for each function call (log n)
- requires efficient random access (bad for linked lists)
- complexity: average case: n log n (e.g. 1000: 1000 * log(1000) = 1000 * 10 = 10.000)
- worst case: n^2 (like selection sort), but it is extremely unlikely (e.g. 1000: 1000 * 1000 = 1.000.000)
  - same as selection sort

## Divide et Impera
> Divide and rule
- In Programming and Politics used as "Divide and Conquer".

<img width="264" alt="image" src="https://user-images.githubusercontent.com/7360266/150950995-a8964711-0085-4305-9925-a2e796e49925.png">


This is a technique phrased and used by Julius Caesar to conquer his enemies:
> Break up larger concentrations of power into pieces that individually have less power than the one implementing the strategy.

<img width="983" alt="image" src="https://user-images.githubusercontent.com/7360266/150951168-c584d386-3678-408c-bbbc-028e7e44964b.png">


How To Eat an Elephant?
> One bite at a time.
- For us it's "One Byte at a time". Hehe.

These wisdoms both follow one idea: Don't get overwhelmed by one giant problem. Either 
- split it up into multiple small problems and solve them one at a time
- or just get at it bit by bit in a row

These wisdoms apply to almost any other field of life, too.

I often like to think of programmers as problem-solvers. The techniques that we apply at solving software problems can often be applied to other areas as well. You need to solve a problem? Find an algorithm. Sounds nerdy, but it's sort of true.
