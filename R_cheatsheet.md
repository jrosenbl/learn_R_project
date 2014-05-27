R Cheatsheet
============

Sourced from Coursera Johns Hopkins University, "R Programming" online course

misc
----

**str(x)** - display the structure of x  
**summary(x)** - do summary statistics on x  
**invisible(x)** - return x but don't print it  

data
----
**library(datasets)**  
**data(_datasetName_)**  
**gl(_factorLevels_,_repeatEachFactor_)**  

simulation
----------
**rnorm()** - generate random Normal variates with a given mean and std deviation   
**rbinom()** - generate random binomial distribution
**dnorm()** - evaluate Normal probability density (with a given mean/SD) at a point (or vector of points)
**pnorm()** - evaluate the cumulative distribution function for a Normal distribution
**rpois()** - generate random Poisson variates with a given rate
**every distribution has these 4 functions:**  
  - d for density
  - r for random num density
  - p for cumulative dist
  - q for quantile function
**set.seed(_seed_)** - always set the seed for reproducible results  
**sample(_vector_, _numSamples_, replace=FALSE)** - replace=TRUE allows repeated values in sample. w/o _numSamples_ returns permutation of _vector_  

apply functions 
---------------
**lapply(<list>, <function>, <...>)*** - apply the function to each element in the list. always returns a list 
examples:
   - x = list(a=1:5, b=rnorm(10))
   - lapply(x,mean)  
   - lapply(x, function(elt) elt[,1])  # where x is a list of matrices  
   -   returns a list of 2 elements each containing the first column of each matrix

**sapply** will try to simplify the result of lapply where possible:
  - if result is a list where every element is of length 1, simplify to vector
  - if result is a list where every element is a vector of the same length (>1) a matrix is returned
  - otherwise return the list

**apply(x, margin, fun,...)** - apply a function (often anon) over the margins (rows or columns) of an array
examples:  
  - apply(x, 2, mean) - return the mean of the columns of matrix x
  - apply(x, 1, mean) - return the mean of the rows of matrix x

  shortcuts for this type of use:
  - rowSums = apply(x, 1, sum)
  - rowMeans = apply(x, 1, mean
  - colSums = apply(x,2, sum)
  - colMeans = apply(x,2,mean)

  debugging
  ---------

  **traceback()**  
  **trace()**  
  **debug()**  
  **browser()** - insert debuggerbreakpoints in code.  brower commands:
  - n - step
  - _variable_ - display variable
  - ls() - list all names (as usual)
  - c - continue execution  
  **recover()**
  - options(error = recover) - upon error, choose an execution frame and enter Browser in that frame
