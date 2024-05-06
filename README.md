# 202 Sorting

## Introduction

Imagine, we had a List of 1 Million citizens. And we had to find one specific one from that collection. We know the citizen's name. How long would it take us to find that citizen?

Depends on where in the List the citizen is placed. And from where we start searching. Let's assume that it takes 1ms to look at one entry of the List and compare the entry's name with the name that we're looking for.

If we were to start looking from the front, then either:

1. We're lucky (Best-Case Scenario) and it's the first entry of the list. It would take us 1ms to find him.
2. We're unlucky (Worst-Case Scenario) and it's the last entry of the list. It would take us 1 Million ms to find him.
3. We're averagely lucky (Average-Case Scenario) and it would take us about 0.5 Million ms to find him. (Little Quiz: what's the exact average?)
<details>
  <summary>Solution</summary>
  
- 500,000.5ms
</details>

What do you think is the most important number of these?

<details>
  <summary>Solution</summary>
  
- All of them, depending on the situation. But often, the Worst-Case-Scenario is the most important one.
</details>

What would make finding one of these 10 Million citizen easier?

<details>
  <summary>Solution</summary>
  
- If the List was sorted. Like in a Phone Book. If you were searching for a person named Peter, you could check the middle of the Phone Book and see, what letter is printed there. if it's T, then you check the left half of the book, if it's N, then you check the right half of the book etc.
</details>

How long would it take a smart algorithm to find ANY of these 1 Million Citizen if they were sorted?

<details>
  <summary>Solution</summary>
  
- A maximum of 20ms. Yes, that's a crazy improvement.
</details>

That's how powerful sorted lists can be. And smart Algorithms. Now, that you have understood the importance of these, let's look at how we can get our stuff sorted.


## Passing Criteria
- Implement `BubbleSort` and `SelectionSort` including Unit Tests.

## Excellent Criteria
- Implement `QuickSort` instead

## Bonus (Easy)
- Compare the Speed of the algorithms using `System.Stopwatch` (C#) or `std::chrono::high_resolution_clock`.
  - For random, unsorted lists.
  - For reverse-sorted lists.
  - For sorted lists.

## Bonus (Hard)
- Can you implement the Algorithms in a way that they work for your `TurboList`, but also a `System.Array`, a `System.Collections.Generic.List` (C#) or `std::vector` (C++) and your `TurboLinkedList`?
  - Hint (C#): Use the Interface `System.Collections.Generic.IList<T>`
  - Hint (C++): Use Template Programming / Compile-time polymorphism

## Bonus (Hard)
- Can you make the Algorithm Generic? Meaning, that it works for `List<int>` but also `List<char>` and `List<string>`?
  - Hint (C#): Use the Interface `IComparable` or `IComparer`
  - Hint (C++): It is actually a lot easier than in C#. As a bonus, you could look at modern C++ Feature named `concept`