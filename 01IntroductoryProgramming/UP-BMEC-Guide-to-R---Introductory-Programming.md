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

------------------------------------------------------------------------

# This module is still under construction!

Changes were pushed to test committing in GItHub.

Don’t worry, the rest of the module will be up soon!

------------------------------------------------------------------------

## License and Copyright

Copyright (c) 2026 UP Biomedical Engineering Circle.

This project is licensed under the terms of the MIT license.
