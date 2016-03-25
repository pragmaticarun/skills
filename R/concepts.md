#Atomic classes

1. Character
2. Numeric
3. Integer
4. Complex
5. Logical

#Collections

1.  Vector(Homogeneous)
2.  Lists(Heterogeneous)

##List Elements

Uses double brackets to index elements.

#Matrix

Vectors with dimensions nrow and ncol
Values filled with column wise.

Can be created by adding dimensions attribute to the vector.

#Factors

Used for storing categorical data
Can be visualised to be integer vector with name for each element.

lm and glm functions treats them special.

Factors can be ordered or unordered.

#Data Frames
Used to store tabular data
Each element is column and number of elements comprise row. Columns can be of different types.

Can be thought of as collection of lists with same length and each column are of similar types. 

*vectors* <=> *matrix*
*lists*   <=> *data frames*

#Reading Data

1.   read.table - reading tabular data
2.   read.csv - reading tabular data
3.   readLines - for reading in text file
4.   source - for reading in R code file
5.   dget   - for reading in R code file
6.   load - for reading in saved workspaces
7.   unserialize - for reading single R objects in binary form.

# Reading Larger datasets
1.  comment.char = ""
2.  Specify colClasses
3.  Know thy system
4.  Calculate memory requirements

#Textual data formats
Includes metadata.

1.  dump <=> source
2.  dput <=> dget

#Connection to the outside word

Data are read through connection interface
1.  file
2.  gzfile
3.  bzfile
4.  url

#Subsetting
1.   [  - returns same class of object, can be used to subset multiple elements
2.   [[ - used to extract one element a list or dataframe . Can be used for computed names.
3.   $ - can be used to extract elements of list by name, applies only for literal name.


#Functions

##Argument Matching
All named arguments are first taken off
All the others are matched based on the order of the appearance

The argument names can be partially matched.
1.  Check for exact match
2.  Check for a partial match
3.  Check for a positional match

##Lazy Evaluation

Arguments are evaluated only as needed.

```R
f<-function(a,b) {
   a^2
}
```

##Ellipsis
All arguments following ellipsis must be named in full.

##Scope
1.   Global workspace
2.   Loaded Package

R has separate name spaces for variables and functions

R uses lexical scoping

## Free variables
Variables used in the function which are not part of formal arguments.

## Closure
A function  + an environment is called a closure or function closure.

1.   Global Environment
2.   Parent Environment 
3.   Until Empty Environment.

#Looping functions

Apply a function on list of elements

1. lapply - always returns a list.
2. sapply - simplify the list returned into vector or matrix.
2. apply  - evaluate a function on rows or columns
3. mapply - evaluate a function over multiple arguments
5. tapply - used to apply a function over subsets of the vector.
6. split - not a loop function but splits a object into groups based on factors.

#Debugging functions

1.  `traceback` - prints out the function call stack after an error occurs
2.  `debug` flags a function as debug
3. `browser` suspends the executing of a function whereever it is called and puts in debug mode.
4.  `trace` allows you to insert debugging code into a function at specific places
5.  `recover` allows you to modify the error behavior so that you can browse the function call stack.

#Simulation

##Probability Distribution

1.  Normal
2.  Poisson
3.  Gamma
4.  Uniform

##Functions

1. norm
2. pois
3. unif
4. gamma

##Prefixes

1.  d - density
2.  r - Random number generation
3.  p - Cumulative distribution
4.  q - Quantile function
