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
    - [Character](#character)
    - [Numeric](#numeric)
    - [Integer](#integer)
    - [Logical](#logical)
    - [Complex](#complex)
    - [Raw](#raw)
  - [Data Structures](#data-structures)
    - [Vectors](#vectors)
    - [Lists](#lists)
    - [Matrices](#matrices)
    - [Dataframes](#dataframes)
    - [Class Identification](#class-identification)
  - [Logic and Control Flow](#logic-and-control-flow)
    - [Conditional Statements](#conditional-statements)
    - [Logical Operators](#logical-operators)
    - [Loops](#loops)
  - [Troubleshooting](#troubleshooting)
    - [Documentation](#documentation)
    - [Common Error Messages](#common-error-messages)
    - [Tips for Fixing Errors](#tips-for-fixing-errors)
  - [Final Messages](#final-messages)
  - [Contributors](#contributors)
  - [License and Copyright](#license-and-copyright)

# Introductory Programming

Welcome to the first module!

R has a lot of capabilities when it comes to data analysis and machine
learning, but it’s first important to understand the basics.

------------------------------------------------------------------------

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

To check your working directory (i.e. where all your files are, we use
`getwd()`.

``` r
getwd()
```

    ## [1] "C:/Users/Mike/Desktop/BMEC/R-Data-Science-Guide/01IntroductoryProgramming"

You can use `setwd()` to manually set your directory, but this is an
archaic way. Instead, we now use the *New Directory* method set earlier.

------------------------------------------------------------------------

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

------------------------------------------------------------------------

## Data Types

Before creating data structures, it is important to first know core data
types in R. There are six atomic data types, which are the fundamental
datatypes we will be working with.

### Character

This data is meant for text. To create a value of the character data
type, simply wrap the text (or even number) in single or double quotes.

``` r
my_character1 <- "hello"
my_character2 <- "101"
```

To convert from one data type to the character data type, we use
`as.character()`.

``` r
my_character3 <- as.character(67)
print(my_character3)
```

    ## [1] "67"

Notice that the number has quotes around it!

### Numeric

This acts as the default type for any number, whether or not it has a
decimal.

``` r
my_numeric1 <- 3.14
my_numeric2 <- 150
```

We use `as.numeric()` to convert to a numeric data type; we’ll use this
to convert `my_character3` back into numeric data.

``` r
my_numeric3 <- as.numeric(my_character3)
print(my_numeric3)
```

    ## [1] 67

The quotes have now disappeared.

### Integer

Integers are for data without decimal places.

``` r
my_integer1 <- 120L
my_integer2 <- 50L
```

Once again, we can use `as.integer()` to convert `my_character2`.

``` r
my_integer3 <- as.integer(my_character2)
print(my_integer3)
```

    ## [1] 101

When dividing integers, the final value will be in the numeric data
type. However, you can specify to fetch the quotient in integer form
with integer division.

``` r
# Normal division (returns a numeric value)
my_integer1 / my_integer2
```

    ## [1] 2.4

``` r
# Integer division (returns an integer value)
my_integer1 %/% my_integer2
```

    ## [1] 2

``` r
# Remainder (Returns an integer value)
my_integer1 %% my_integer2
```

    ## [1] 20

To get the floor and ceiling values, we use, well, `floor()` and
`ceiling()`.

``` r
floor(my_numeric1)
```

    ## [1] 3

``` r
ceiling(my_numeric1)
```

    ## [1] 4

### Logical

This is made of true or false statements (in uppercase), and will be
used during data manipulation and filtering later on.

``` r
is_weekday <- TRUE
is_weekend <- FALSE
print(is_weekday)
```

    ## [1] TRUE

``` r
print(is_weekend)
```

    ## [1] FALSE

``` r
# Shortcuts can also be used
is_daytime <- T
is_nighttime <- F
print(is_daytime)
```

    ## [1] TRUE

``` r
print(is_nighttime)
```

    ## [1] FALSE

More than often though, the way to generate logical values is by
comparing values through logical operators. We’ll go into more detail on
this later, but here is a short demonstration just to show the
capabilities:

``` r
# Check if values are equal
5 == 10
```

    ## [1] FALSE

``` r
5 != 10
```

    ## [1] TRUE

``` r
# Check for size comparison
5 < 10
```

    ## [1] TRUE

``` r
5 <= 10
```

    ## [1] TRUE

``` r
5 >= 10
```

    ## [1] FALSE

``` r
5 > 10
```

    ## [1] FALSE

``` r
# Check if in a vector
"Red" %in% c("Red", "Orange", "Yellow")
```

    ## [1] TRUE

### Complex

The complex data type is used to store complex numbers, but this won’t
really be used.

``` r
# Storing real + imaginary value
my_complex1 <- 5 + 6i
print(my_complex1)
```

    ## [1] 5+6i

``` r
# Storing just imaginary value
my_complex2 <- 7i
print(my_complex2)
```

    ## [1] 0+7i

### Raw

The raw data type is meant to store binary data, and is meant for
low-level processing.

``` r
# Generating raw vector of length 10
my_raw1 <- raw(10)
print(my_raw1)
```

    ##  [1] 00 00 00 00 00 00 00 00 00 00

``` r
# Converting text to raw bytes and vice versa
my_raw2 <- charToRaw(my_character1)
print(my_raw2)
```

    ## [1] 68 65 6c 6c 6f

``` r
rawToChar(my_raw2)
```

    ## [1] "hello"

------------------------------------------------------------------------

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

### Class Identification

To check for the classification of values, we can either use `class()`
or `typeof()`. Using `class()` gives us the high-level, general data
type, while `typeof()` gives the low-level, internal data type. This
could be better understood through a demonstration.

``` r
type_test <- data.frame(id = 1:2, name = c("A", "B"))
class(type_test)
```

    ## [1] "data.frame"

``` r
typeof(type_test)
```

    ## [1] "list"

We can see that running `class()` gives us “data.frame”, letting us know
that R treats type_test as a dataframe. However, a dataframe is also
just a list of vectors, which is the value given by `typeof()`.

------------------------------------------------------------------------

## Logic and Control Flow

The final part of this module will focus on logic and control flow.
Control statements run a code block based on what condition is met.

### Conditional Statements

Below is an if-else statement, which essentially says “if this condition
is met, do this; otherwise, do this.”

``` r
score <- 79.45

if (score >= 92) {
  print("Grade: 1.00")
} else if (score >= 88) {
  print("Grade: 1.25")
} else if (score >= 84) {
  print("Grade: 1.50")
} else if (score >= 80) {
  print("Grade: 1.75")
} else if (score >= 76) {
  print("Grade: 2.00")
} else if (score >= 72) {
  print("Grade: 2.25")
} else if (score >= 68) {
  print("Grade: 2.50")
} else if (score >= 64) {
  print("Grade: 2.75")
} else {
  print("Grade: 3.00 and below")
}
```

    ## [1] "Grade: 2.00"

Above is a code snippet that allows you to classify a student’s grade. I
suggest changing the values to see how the score fits into various
cases. *The `else` or `else if` statement must always sit on the same
line as the closing curly brace of the previous block.*

### Logical Operators

There are several logical operators:

- `&` (AND) - **Both** conditions must be true.

- `|` (OR) - **At least one** condition must be true.

- `!` (NOT) - Changes value from true to false or vice versa.

``` r
# Demonstration #1
age <- 24
has_id <- TRUE

if (age >= 18 & has_id == TRUE) {
  print("Can drink alcohol!")
} else {
  print("Cannot drink alcohol!")
}
```

    ## [1] "Can drink alcohol!"

``` r
# Demonstration #2
is_engg_student <- FALSE
is_not_engg_student <- TRUE

if (is_engg_student == TRUE || is_not_engg_student == TRUE) {
  print("Can join BMEC (we're university-wide)!")
} else {
  print("Cannot join BMEC!")
}
```

    ## [1] "Can join BMEC (we're university-wide)!"

### Loops

Loops are used to repeat a block of code multiple times based on a
condition.

#### For Loops

A `for` loop is to set a specific number of times to repeat a code
block. We can set this through a sequence of numbers.

``` r
# Loop through a sequence of numbers
for (i in 1:5) {
  print(paste("Iteration number:", i))
}
```

    ## [1] "Iteration number: 1"
    ## [1] "Iteration number: 2"
    ## [1] "Iteration number: 3"
    ## [1] "Iteration number: 4"
    ## [1] "Iteration number: 5"

We can also loop through all values in a vector.

``` r
# Loop through a character vector (using fruits vector from earlier)
print("Ice Cream Flavors:")
```

    ## [1] "Ice Cream Flavors:"

``` r
for (fruit in fruits) {
  print(paste(fruit, "Ice Cream"))
}
```

    ## [1] "Blueberry Ice Cream"
    ## [1] "Apple Ice Cream"
    ## [1] "Orange Ice Cream"
    ## [1] "Strawberry Ice Cream"
    ## [1] "Banana Ice Cream"
    ## [1] "Grapes Ice Cream"
    ## [1] "Kiwi Ice Cream"

#### While Loops

Use a `while` loop to repeat code while a certain condition remains
`TRUE`. Ensure that the condition eventually becomes `FALSE` to prevent
an infinite loop.

``` r
payment_no <- 1

while (payment_no <= 3) {
  print(paste("Payment No.:", payment_no))
  payment_no <- payment_no + 1 # Adds an increment
}
```

    ## [1] "Payment No.: 1"
    ## [1] "Payment No.: 2"
    ## [1] "Payment No.: 3"

``` r
print("You reached the maximum number of payments!")
```

    ## [1] "You reached the maximum number of payments!"

------------------------------------------------------------------------

## Troubleshooting

Knowing how to deal with documentations and errors is an important part
of learning how to code, hence what this section is for.

### Documentation

You can access documentation help from RStudio itself in the *Help*
section. You can view what a function or package does. To search for a
function, use `?[function]` or `help()`. To search for a package,
specify its name within the `help()` function.

``` r
# Opens documentation for a function
?mean
help(mean)

# Opens documentation for a package
help(package = "ggplot2")

# Search for a specific keyword across all installed packages
??regression
```

### Common Error Messages

“Error: object ‘x’ not found”

- This means that R has no record of a variable or function with that
  name.
- To fix, check for typos (including if you are using the correct case),
  or ensure you have run the line of code that defines the object.

“Error: unexpected ‘}’” (or unexpected symbol)

- This may indicate mismatched left-hand-side and right-hand-side
  brackets, parentheses, or braces. It may also indicate missing commas
  or a misspelled function.
- To fix, look at the line number in the error message and trace for the
  opening grouping symbol to see if they are properly closed.

“Warning message: NAs introduced by coercion”

- This is a warning, not an error. During data type conversion, there
  were some values that R could not convert, so they were instead turned
  into missing values (`NA`).
- Check your source data and perhaps identify an approach for either
  dealing with `NA` values altogether or changing your data manipulation
  method beforehand. For example, `as.numeric("apple")` will trigger the
  warning.

### Tips for Fixing Errors

1.  Read the error message closely. Look for file names, line numbers,
    or specific function names mentioned. Stack Overflow and AI chatbots
    will also be your best bet during debugging.
2.  Sometimes old variables clog up memory, so head to *Session* **\>**
    *Restart R* to restart.
3.  For dealing with numeric data, use `str(your_data)` to ensure your
    numbers are actually formatted as numbers and not characters.

------------------------------------------------------------------------

## Final Messages

Congratulations on completing the first module! You now know how to deal
with basic programming in R. The next module will focus on data cleaning
and manipulation, wherein you’ll learn:

- Importing and exporting various file types

- Filtering, sorting, and cleaning data

- Using the `tidyverse` collection of packages and understanding its
  syntax

The next modules will now have more hands-on examples as well; if some
topics here may not seem fully tangible, you’ll understand them more
through applying them as you work with your first dataset!

On a more personal note, thank you for taking the time to go through the
very first module of Bio-informed. As the person in charge of
spearheading the bioinformatics division, it had always been a dream of
mine to be able to contribute to education and research in data science,
especially as someone with a non-statistics/CS/math degree. I consider
data to be my first love, and I hope that these resources may help give
you the skills to pursue your own projects, no matter how niche the
topic may be.

I hope that the module was understandable for beginners, and if you have
any suggestions, concerns, or questions, you may reach me at my email:
<samnicole.gianan@gmail.com>. Alternatively, you may reach me at
**greywolffles** on Discord or [Sam Gianan](m.me/sam.gianan.98) on
Messenger. I’d also love to hear about any projects you may be working
on!

Again, thank you for looking through our guide, and I hope to see you in
the next one, coming soon!

— Sam Gianan, UP BMEC Bioinformatics Head

------------------------------------------------------------------------

## Contributors

- [Sam Gianan](github.com/greywolffles)

------------------------------------------------------------------------

## License and Copyright

Copyright (c) 2026 UP Biomedical Engineering Circle.

This project is licensed under the terms of the MIT license.
