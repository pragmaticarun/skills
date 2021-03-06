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

##Lexical scoping
Free variables are looked at the environment in which the functions are defined.

##Dynamic scoping
Free variables are looked in the environment in which the functions are called.

##Parent frame.
The environment in which the function is called.

## Object Storage
All objects should be stored in the memory.

#Date and Time

Date class 
No of days since 1/1/1970
Time has two classes POSIXct and POSIXlt
No of seconds since 1/1/1970


##POSIXct


##POSIXct
=======
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

#data.table


No column subscripting
Data tables are copied by reference so no new copy is made.

#dplyr

##Verbs
1. select - return subset of columns
2. filter - extract subset of rows based on conditions
3. arrange - reorder rows of dataframe
4. rename  - rename variables n a data frame
5. mutate  - add/transform variables
6. summarise/summarize - generate summary of statistics.


#Hierarchial Clustering

*   How do we define close ?
*   How do we group things ?
*   How do we visualize the grouping ?
*   How do we interpret the grouping ?

1. Find the closest two things
2. Put them together
3. Find the next closest

Requires

1. A defined distance
   a.  Continuous - Euclidean distance
   b.  Continuous - Correlation similarity
   c.  Binary     - Manhattan distance

2. A merging approach
   a. Complete
   b. Average


#K means Clustering

1. Fix numner of clusters
2. Get centroids of each cluster
3. Assign things to the closest centroid
4. Recalculate centroids

Requires

1. A defined distance metric
2. Number of clusters
3. An initial guess as to cluster centroids

Final estimate

1. Final estimate of cluster centroids
2. An assignment of each point to clusters


#Colors

RColorBrewer package
1. Sequential
2. Diverging
3. Qualitative
