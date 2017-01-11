Getting to know R(Studio)
========================================================
author: Kendra Maas
date: Jan 12, 2017


Software we'll use
===========
incremental: true

- R is the language
- RStudio is a really nice GUI that makes working in R easier
    - You don't have to use RStudio to use R in your real life, but you do have to use it in this class
- git is a version control program, GitHub is a popular website for storing and sharing your git repos
- RStudio makes using git/GitHub with R easier

- [viz workshop github](https://github.com/krmaas/r.viz.2017/settings)


EtherPad
========================================================
This is public, but I've used it in other software workshops and found it useful. I suggest using it when you are having issues with a command, post exactly what you are typing here so everyone can try to help you troubleshoot.

[etherpad] (https://public.etherpad-mozilla.org/p/wyBm0STw1E)

Stickies

Console
========================================================
incremental: true

- Command line
- > prompt
- creating and object in R


```r
objectName <- values
```


```r
x <- 2+3
```


```r
x
```

```
[1] 5
```

========================================================
incremental: true


```r
objectName <- values
```

- Read this objectName "gets" values

- shortcut Alt + - or Option + -

- can use = but this can lead to confusion when dealing with options

- There are lots of [keyboard shortcuts](https://support.rstudio.com/hc/en-us/articles/200711853-Keyboard-Shortcuts) to make your life easier
    + ctrl + Enter sends commands from Editor to Console
    + ctrl + `1` sends cursor to Editor
    + ctrl + `2` sends cursor to Console


Names matter
==================
incremental: true
- No spaces, commas, alphanumeric + . + _
- Names and variables must start with a letter
- File name includes the path, if you're not entering path info it is assumed that the file is in the working directory


```r
getwd()
```

```
[1] "C:/data/short_courses/R_vis/r.viz.2017"
```

More Names
============

- Options for naming objects (files, variables, etc)

```r
lowerCamelCase
UpperCamelCase
i.use.periods
or_sometimes_underscores
```
Pick one of the naming conventions and try to stick with it
- Do as I say not as I do

Try a few more
================
incremental: true

```r
r.rocks <- 2^4
```

```r
rRocks
```
```
Error: object 'rRocks' not found
```

```r
r.rocks
```

```
[1] 16
```
* Implicit contract with the computer or scripting language: Computer will do tedious computation for you. In return, you will be completely precise in your instructions.

Object types
========================================================
incremental: true
R has 5 basic (atomic) classes of objects

- numeric
- integer
- character
- complex
- logical (true/false)

Numbers
========================================================
incremental: true
* Numbers are generally treated as numeric unless specifically designated as integers
* `Inf` is a special number, can be used in calculations
    + `1/0` = `Inf`
    + `1/Inf` = `0`

* `NaN` is another special number, can be the result of calculations
    + `0/0` = `NaN`
    + I like `NaN` for missing variables

Factors
========================================================
incremental: true
* Can be letters/words or numbers
* USE WORDS, make your life easier when you open the file in 6 months
* Caution, values are stored as numbers.  Can be coerced into acting like numbers
* Order is automatically sorted but you can reorder

===================================================
incremental: true

Basic object is vector (atomic vector)
  + Vector only has one class

```r
r.rocks
```

```
[1] 16
```

```r
seq(1,5)
```

```
[1] 1 2 3 4 5
```
 
  + RStudio stored vectors under "Values"
  + Do you see a vector for the seq(1,5) operation?

Object Attributes
=======================================================
incremental: true
Objects can have attributes
* names, dimnames
* dimensions
* class
* length
* user defined metadata

Metadata
====================
![princess bride metadata](metadata.jpeg)
> Metadata - Data about the data  
> Who, what, where, when, how of data generation  
> >  i.e. pH is data. The pH meter used, technician, date, location are metadata

Back to Attributes
========================================================
incremental: true
* view the attributes with

```r
attributes(r.rocks)
```

```
NULL
```
* We didn't assign any, and R doesn't automatically assign any for 1 value vectors

```r
str(r.rocks)
```

```
 num 16
```

========================================================
incremental: true

```r
x <- seq(5, 18, 3)
```

```r
y <- cbind(x, r.rocks)
```

========================================================
incremental: true


```r
attributes(y)
```

```
$dim
[1] 5 2

$dimnames
$dimnames[[1]]
NULL

$dimnames[[2]]
[1] "x"       "r.rocks"
```

```r
str(y)
```

```
 num [1:5, 1:2] 5 8 11 14 17 16 16 16 16 16
 - attr(*, "dimnames")=List of 2
  ..$ : NULL
  ..$ : chr [1:2] "x" "r.rocks"
```

========================================================
incremental: true
Try `rbind(x, r.rocks)`

How do the structure and attributes change?

========================================================
incremental: true

c() concatenates values to make a vector

```r
z <- c(1, 32, 13.5)
```


```r
str(z)
```

```
 num [1:3] 1 32 13.5
```

```r
z1 <- c("1", "foo", "TRUE")
```

```r
str(z1)
```

```
 chr [1:3] "1" "foo" "TRUE"
```

* If you mix object types, the vector will be `character`

Common objects  
=======================================================
incremental: true
* Vector
* List
* Matrix
* Array
* Tables
* **Data Frame**

List  
=======================================================
incremental: true
* Vector that can contain objects of different class
* Lists are useful but difficult to understand because they're usually not 2D tables
* Be aware that many functions output lists
* More about lists later

Matrix/Array/Table
=======================================================
incremental: true
* Matrix-2D object
* Array-2D+ object
* Table-usually output, very similar to matrix
* All cells must be same type

Data Frame  
=======================================================
incremental: true
* Most common object you'll work with
* Column = variable =ish vector
* Each Column has same object type
* Columns with different types can be in one data frame
* Often have column and row names
* Becoming the default object type for many packages
* Almost always will be importing these data

=======================================
![jennybc objects flow](object.type.flow.diagram.png)

Accessing bits of data  
=======================================================
incremental: true
* Remember `z`

```r
z
```

```
[1]  1.0 32.0 13.5
```
* What's the first value of the first item in z?

```r
z[1]
```

```
[1] 1
```
* How about the third?

Accessing bits of data  
=======================================================
incremental: true

```r
(m <- matrix(1:16, nrow=4))
```

```
     [,1] [,2] [,3] [,4]
[1,]    1    5    9   13
[2,]    2    6   10   14
[3,]    3    7   11   15
[4,]    4    8   12   16
```

Accessing bits of data  
=======================================================
incremental: true
* What does the second column look like?

```r
m[,2]
```

```
[1] 5 6 7 8
```
* How about 4th row?

```r
m[4,]
```

```
[1]  4  8 12 16
```
* What number is in the third row, third column?
* Someone post the syntax for finding that on the etherpad
* `object[row,column]` is how you will access all sorts of data

Workspace (aka Environment)
=======================================================
incremental: true

* Where every object you create exists
* Remove objects `rm(x)`
* Remove all objects `rm(list=ls())
* Once you close R, everything in the workspace (and history) disappears
    + This is usually a good thing, don't save all the intermediate files
    + You can save your workspace as .RData
* Save individual (final) result to the current working directory
    + What is your current directory?  Post it into the etherpad

Better way to manage R
=======================================================
incremental: true
R Projects
* Creates folder in the working directory you set
* .Rproj is the basis for linking RStudio to GitHub
R scripts
* Don't type in the console, type in a script file
    + Track what you've done
    + Easily repeat analyses
    + Don't have to recreate code when someone (often you) wants to do that `thing` again on a new dataset in a few months

Packages
=======================================================
incremental: true
* The reason why R has become the default data analysis language
* Anyone can author a package
    + Must follow documentation guidelines
    + Must contain practice data
    + Most hosted on CRAN 
    + `install.packages("packageName")`
    + Can use anyones in progress code by `source("script.name")`
