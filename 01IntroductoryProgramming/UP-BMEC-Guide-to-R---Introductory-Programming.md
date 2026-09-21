UP BMEC Guide to R - Introductory Programming
================
Sam Gianan
2026-08-31

- [Introductory Programming](#introductory-programming)
  - [Understanding RStudio](#understanding-rstudio)
    - [Panes](#panes)
    - [Creating Your First Project and
      Script](#creating-your-first-project-and-script)
  - [Basic Functions and Variables](#basic-functions-and-variables)
  - [Data Types](#data-types)
  - [Data Structures](#data-structures)
    - [Vectors](#vectors)
    - [Lists](#lists)
    - [Matrices](#matrices)
    - [Dataframes](#dataframes)
- [This module is still under
  construction!](#this-module-is-still-under-construction)
  - [License and Copyright](#license-and-copyright)

# Introductory Programming

Welcome to the first module!

R has a lot of capabilities when it comes to data analysis and machine
learning, but it’s first important to understand the basics.

## Understanding RStudio

### Panes

If you are using RStudio, you will notice that upon launching, there are
three main sections:

<table style="width:100%;">
<colgroup>
<col style="width: 6%" />
<col style="width: 12%" />
<col style="width: 79%" />
</colgroup>
<thead>
<tr>
<th>Location</th>
<th>Name</th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td>Left</td>
<td>Console</td>
<td>Where your live code is ran</td>
</tr>
<tr>
<td>Upper Right</td>
<td>Environment/History/Git</td>
<td><p>Keeps track of variables, dataframes, and commands currently
stored in your computer’s memory</p>
<p>You can also commit changes to GitHub through the <em>Git</em>
section</p></td>
</tr>
<tr>
<td>Bottom Right</td>
<td>Files/Plots/Packages/Help</td>
<td><p>Shows an outline of all files and packages in your project, as
well as generated plots</p>
<p>The <em>Help</em> section may be used to search up documentation for
a function without leaving the IDE through <code>?[function]</code> (try
typing <code>?mean</code> in the console to test it out!)</p></td>
</tr>
</tbody>
</table>

### Creating Your First Project and Script

To follow along, create your first project and script in R!

1.  Click *File \> New Project… \> New Directory*.
2.  Select *New Project* as the project type.
3.  Type a name for your project.
4.  Click *Browse…* to choose a folder to save your project in.
5.  Click *Create Project*.

While you can follow along by writing code in the console, it would be
better to create a file (i.e. an R script) to save and organize your
code.

1.  Click *File \> New File \> R Script*, which will open the *Source*
    pane. This completes the final pane you’ll see in a standard RStudio
    layout.
2.  Inside the *Source* pane, you can now type the obligatory
    introductory code snippet:

``` r
print("Hello world!")
```

    ## [1] "Hello world!"

3.  Run the code with the `Run` button in the upper right corner of the
    *Source* pane.

Bonus things to know to organize your scripts:

- Commenting on your code is good practice for yourself and others to
  understand what your script does. To comment on R:

  - A single-line comment only needs a hashtag, `# like this`!

  - To comment out multiple lines, highlight the lines you want to turn
    into a comment then hit `Ctrl + Shift + C` (Windows/Linux) or
    `Cmd + Shift + C` (Mac).

  - To create sections in your R script, adding four or more consecutive
    hashtags (`####`), hyphens (`----`), or equals signs (`====`) can
    add collapsible headers to your script.

``` r
# This is a single-line comment

# This multi-line comment...
# ...was made with Ctrl + Shift + C

# This makes a new section! ####

# So does this ----

# This too ====
```

## Basic Functions and Variables

We can now move on to introductory programming! To create your first
variable, R actually uses the `<-` operator instead of the more common
`=` operator. For example:

``` r
x <- 1
y <- 2
```

Don’t worry about semicolons at the end of a line! You can use them
though to assign variables in one line:

``` r
a <- 3; b <- 4
```

To delete a variable, we use the `rm()` function:

``` r
rm(y)

# To delete more than one object, just separate them with a comma!

rm(a, b)

# To delete everything in your environment:

rm(list = ls()) 
```

Re-initialize `x` and `y` to use for the next few examples.

Operations can be done in R as demonstrated:

``` r
x <- 1
y <- 2

x + y # Addition
```

    ## [1] 3

``` r
y - x # Subtration
```

    ## [1] 1

``` r
x * y # Multiplication
```

    ## [1] 2

``` r
x / y # Division
```

    ## [1] 0.5

``` r
y %% x # Modulus
```

    ## [1] 0

## Data Types

Before creating data structures, it is important to first know core data
types in R.

## Data Structures

### Vectors

To create a vector, we use c(), which means to combine. A vector must
have the same data type (i.e. all numeric, all logical, all dates,
etc.). Vectors come in handy for data cleaning and manipulation, such as
for searching and filtering.

``` r
fruits <- c("Apple", "Orange", "Banana")
fruits
```

    ## [1] "Apple"  "Orange" "Banana"

To add a new value, you may either use `c()` or the `append()` function.
`append()` is more flexible, as it allows you to add a value in the
middle of a vector, not just at the beginning or at the end.

``` r
# Using c()
fruits <- c(fruits, "Grapes") # Adds at end of a vector
fruits
```

    ## [1] "Apple"  "Orange" "Banana" "Grapes"

``` r
fruits <- c("Blueberry", fruits) # Adds at the beginning of a vector 
fruits
```

    ## [1] "Blueberry" "Apple"     "Orange"    "Banana"    "Grapes"

``` r
# Using append()
fruits <- append(fruits, "Kiwi") # Appends at the end of a vector
fruits
```

    ## [1] "Blueberry" "Apple"     "Orange"    "Banana"    "Grapes"    "Kiwi"

``` r
fruits <- append (fruits, "Strawberry", after = 3) # Appends after 3 elements, making it the fourth item in the vector
fruits
```

    ## [1] "Blueberry"  "Apple"      "Orange"     "Strawberry" "Banana"    
    ## [6] "Grapes"     "Kiwi"

We’ll go more in-depth on what vectors could be used for once we get
into data cleaning and manipulation.

### Lists

Unlike vectors, lists may hold more than one data type. We can create
them with the `list()` function. Lists can also hold vectors, matrices,
dataframes, and even other lists.

``` r
student <- list(
  name = "John Doe",
  age = 18,
  birthday = as.Date("2004-08-13", # We'll go more into the as.Date() function in the next module
  taken_ges = c("Eng 13", "Kas 1", "Speech 30"),
  has_graduated = FALSE
))

str(student) # For printing the list
```

    ## List of 3
    ##  $ name    : chr "John Doe"
    ##  $ age     : num 18
    ##  $ birthday: Date[1:1], format: "2004-08-13"

As observed, various data types can be stored within the student list.

### Matrices

Matrices are two-dimensional by nature with rows and columns. To create
a matrix, you can either (1) use an existing vector and divide it by
column or row, or (b) combine vectors with each acting as a row or
column. The latter is done with `cbind()` or `rbind()`, and can be used
on vectors with different lengths.

``` r
# Vectors for demonstration
vec_1 <- c(1, 2, 3, 4, 5, 6, 7, 8, 9)
vec_2 <- c(1, 2, 3)
vec_3 <- c(1, 2, 3, 4, 5) 

# To fill up a matrix by column
matrix_col <- matrix(vec_1, nrow = 3, ncol = 3)
print(matrix_col) 
```

    ##      [,1] [,2] [,3]
    ## [1,]    1    4    7
    ## [2,]    2    5    8
    ## [3,]    3    6    9

``` r
# To fill up a matrix by row
matrix_row <- matrix(vec_1, nrow = 3, ncol = 3, byrow = TRUE)
print(matrix_row)
```

    ##      [,1] [,2] [,3]
    ## [1,]    1    2    3
    ## [2,]    4    5    6
    ## [3,]    7    8    9

Notice the difference in order of how the matrices are set up.
Furthermore, by default, the byrow argument in the matrix() function is
set to FALSE, so when filling up matrices by column, you do not need to
specify its value.

``` r
matrix_cbind <- cbind(vec_2, vec_3)
```

    ## Warning in cbind(vec_2, vec_3): number of rows of result is not a multiple of
    ## vector length (arg 1)

``` r
print(matrix_cbind) 
```

    ##      vec_2 vec_3
    ## [1,]     1     1
    ## [2,]     2     2
    ## [3,]     3     3
    ## [4,]     1     4
    ## [5,]     2     5

``` r
matrix_rbind <- rbind(vec_2, vec_3)
```

    ## Warning in rbind(vec_2, vec_3): number of columns of result is not a multiple
    ## of vector length (arg 1)

``` r
print(matrix_rbind)
```

    ##       [,1] [,2] [,3] [,4] [,5]
    ## vec_2    1    2    3    1    2
    ## vec_3    1    2    3    4    5

You can notice that since `vec_2` is smaller than `vec_3`, the function
loops the smaller vector’s values to fill up the remaining spaces.
Furthermore as the number of values in `vec_3` is not divisible by the
number of values in `vec_2` (i.e. 5 divided by 3 has a remainder), a
warning will be given, as all of the values in `vec_2` are not looped
through.

If you prefer though that these values are not looped and are instead NA
values, you can set the length of the smaller vector to that of the
larger one, which will cause the placement of NA values.

``` r
max_len <- max(length(vec_2), length(vec_3))
length(vec_2) <- max_len
cbind(vec_2, vec_3)
```

    ##      vec_2 vec_3
    ## [1,]     1     1
    ## [2,]     2     2
    ## [3,]     3     3
    ## [4,]    NA     4
    ## [5,]    NA     5

### Dataframes

Dataframes are the structure that most closely resemble spreadsheets;
they are two-dimensional and can hold more than one data type.

``` r
name_vec <- c("Elijah", "Hannah", "John")
age_vec <- c(18, 20, 19)
university_vec <- c("University of the Philippines - Diliman", "De La Salle University", "University of Santo Tomas")

my_df <- data.frame(
  name_vec, age_vec, university_vec
)

print(my_df)
```

    ##   name_vec age_vec                          university_vec
    ## 1   Elijah      18 University of the Philippines - Diliman
    ## 2   Hannah      20                  De La Salle University
    ## 3     John      19               University of Santo Tomas

This is the type you’ll be working with when handling actual data from
existing datasets!

------------------------------------------------------------------------

# This module is still under construction!

Changes were pushed to test committing in GItHub.

Don’t worry, the rest of the module will be up soon!

------------------------------------------------------------------------

## License and Copyright

Copyright (c) 2026 UP Biomedical Engineering Circle.

This project is licensed under the terms of the MIT license.
