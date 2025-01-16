# Silent Truncation of Logical Vector in R Data Frame Subsetting

This repository demonstrates a subtle bug in R related to subsetting data frames using logical vectors. When a logical vector is longer than the number of rows in the data frame, R silently truncates the vector instead of issuing a warning. This can lead to unexpected and hard-to-debug errors.

## Bug Description
The provided R script attempts to subset a data frame using a logical vector that exceeds the number of rows.  Instead of producing an error or warning, R quietly truncates the logical vector, leading to incorrect subsetting. This behavior is inconsistent with typical R error handling. 

## Solution
The solution involves explicitly checking the length of the logical vector and issuing a warning if it's longer than the data frame. If it is longer it truncates the vector and provides a more informative message to the user.  This makes the code's behavior more predictable and robust.

## How to reproduce:
1. Clone this repository.
2. Run `bug.R` . The result will be a subsetted data frame, but not the one expected given the longer logical vector.
3. Run `bugSolution.R` to see the corrected behavior which contains a warning.