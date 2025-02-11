# Unexpected Return Value in Tcl Procedure

This repository demonstrates a subtle bug in a Tcl procedure related to its return value handling.  The `badproc` procedure in `bug.tcl` incorrectly handles the case when the input `a` is 0.  The solution, provided in `bugSolution.tcl`, addresses this issue.

## Bug Description
The original `badproc` procedure uses `if {$a == 0} {return 1} {return $a + $b}`. This is problematic because, even though the `if` condition is met, the code proceeds to execute `return $a + $b`, potentially returning unexpected results. This is not a syntax error, but rather a logic error resulting from how Tcl interprets and executes the code. 

## Solution
The `bugSolution.tcl` corrects this logic. The fix involves using the correct conditional structure and ensuring that only one return statement is used per branch to avoid unexpected behaviors.