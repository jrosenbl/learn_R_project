
R Cheatsheet
============

Sourced from Coursera Johns Hopkins University, "R Programming" online course

misc
----

**str(x)** - display the structure of x  
**summary(x)** - do summary statistics on x  
**invisible(x)** - return x but don't print it  

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
