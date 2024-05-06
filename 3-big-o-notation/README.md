# Measure Performance (Easy)
- Compare the Speed of selection sort and upcoming algorithms using `System.Stopwatch` (C#) or `std::chrono::high_resolution_clock` (C++).
  - For random, unsorted lists.
  - For reverse-sorted lists.
  - For sorted lists.
- Run the tests
  - for lists of different sizes
    - 100 items
    - 100000 items
  - a couple hundred times in a row
  - and take the average
    - bonus: remove results that are more than 10% off from the median

Pseudo-Code:
```
Time_Results := Empty List

Repeat 101 times:
  Test Data := Create_Test_Data()
  
  # we only want to measure the time that the algorithm takes
  Start_Time_Measure()
  Run The Algorithm Using Test Data
  Stop_Time_Measure()
  
  Add Measured_Time to Time_Results
End Repeat

# sort the results, so we can take the median from the middle of the list
Sort Time_Results()
Median := Time_Results At Index 50

Added_Results := 0
Result_Count := 0

# iterate through all results
For(i := 100...0) Do

  # find out whether the deviation is higher than 10%
  Time_Result := Time_Results At Index i
  Ratio := Absolute(Time_Result / Median)
  If Ratio < 1.1 And Ratio > 0.9 Then
     
     # if not, then we take this result into our averages
     Add Time_Result to Added_Results
     Increment Result_Count
  End If
End For

Average_Result = Added_Results / Result_Count
```