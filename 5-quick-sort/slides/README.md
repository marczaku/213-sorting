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
function partitionFunc(left, right, pivot)
   leftPointer = left
   rightPointer = right - 1

   while True do
      while A[++leftPointer] < pivot do
         //do-nothing            
      end while
		
      while rightPointer > 0 && A[--rightPointer] > pivot do
         //do-nothing         
      end while
		
      if leftPointer >= rightPointer
         break
      else                
         swap leftPointer,rightPointer
      end if
		
   end while 
	
   swap leftPointer,right
   return leftPointer
	
end function

procedure quickSort(left, right)

   if right-left <= 0
      return
   else     
      pivot = A[right]
      partition = partitionFunc(left, right, pivot)
      quickSort(left,partition-1)
      quickSort(partition+1,right)    
   end if		
   
end procedure
```

</details>

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