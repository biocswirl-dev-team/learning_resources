---
title: "CSHL Intro to RNASeq with BiocSwirl Workshop"
author: "Almas K."
date: "30/01/2021"
output:
  html_document:
    keep_md: true
    toc: true
    toc_depth: 3
    toc_float:
      collapsed: true
      smooth_scroll: true
    number_sections:  true
    theme: paper
    self_contained: yes
editor_options: 
  chunk_output_type: inline
---

## Accreditation

Adapted from the following resources:

-   [Data Wrangling workshop](https://github.com/BCCHR-trainee-omics-group/StudyGroup/tree/master/workshops/2020-07-23_data_wrangling_ak) for the BC Children's Trainee Omics Group (TOG) by Almas Khan
-   Also Adapted from Tutorials of Victor Yuan for the BC Children's TOG.
-   [Perdue's Intro to R](https://www.stat.purdue.edu/bigtap/online/docs/Introduction_to_R_and_Bioconductor.html)
-   [DataMentor.io R tutorial](https://www.datamentor.io/r-programming/matrix/)

## About

-   Authors of this script: Almas Khan and Julia Philipp

## Setup

-   Please have the latest version of R and Rstudio installed.

# Overall Learning outcomes

-   Knowledge of R and Bioconductor

-   Knowledge of basic R data types

-   Differentiate a matrix and data.frame

-   Understanding how to :

    -   Assign variables
    -   Run built in operations in R
    -   Subset on a data.frame and matrix

<!---The following chunk allows errors when knitting--->



## Additional Resources:

-   [R Swirl](https://swirlstats.com/) for interactive lesson on programming with R
-   [R for data science](http://r4ds.had.co.nz/) : A comprehensive introductory ebook on R.
-   [Learnr package](https://rstudio.github.io/learnr/) another interactive lesson within R on programming

## Topics

### Part 1: Intro to R:

**What is R ?**

-   What is R markdown?

-   What are vectors and `matrix` objects?

    -   Basic data types
    -   Basic functions for matrices

-   `data.frame`

    -   Basic functions for exploring dataframes

    -   Indexing and Subsetting

-   Common R operations

-   Where to get help

-   Accrediting code

### Part 2: Bioconductor and RNAseq

**What is Bioconductor?**

-   Introduction

**What is BiocSwirl**

-   Introduction
-   Notes and topics

# Part 1: Intro to R

## What is R and what is R markdown?

-   R is an open sourced statistical programming language based on an older proprietary language known as S.

-   R contains various add ons known as packages. Think of these like additional apps on that you download on top of the base apps you get on your phone.

-   We will go over the basics of syntax within R.

But first, let's talk about the document we are currently working in. Think of it as a like a notebook for your code that includes comments and I find it's easier to keep track of your analysis.

I recommend using **r markdown files** for all of your analysis scripts.

In `.rmd` files, code needs to be in code chunks (insert code chunk shortcut is Windows: `ctrl` `+` `alt` `+` `i`, Mac: `cmd` `+` `alt` `+` `i`) in order to run.



In an R markdown you can knit a file into various formats for nice reports.

## Data Types: Vector

In R, the basic data structure is known as a vector. Vectors are divided into various categories.

A few of the basic categories are listed below:

 Use Windows: `ctrl` `+`enter`, Mac:`cmd` + `enter` to run a single line of the code chunk. If there is multiple lines of code you can run the entire chunk using the play button (green triangle) on the code chunk. 


```r
3.14 # This is a numeric vector
```

```
## [1] 3.14
```

```r
"This is a character" # A character vector
```

```
## [1] "This is a character"
```

```r
"3.14" # This is also a character vector
```

```
## [1] "3.14"
```

```r
TRUE # logical vector
```

```
## [1] TRUE
```

```r
FALSE # also logical
```

```
## [1] FALSE
```



```r
FILL_THIS_IN(3.14)
```

```
## Error in FILL_THIS_IN(3.14): could not find function "FILL_THIS_IN"
```

What if we wanted to use a value again?

We can store it as an object.

An object is assigned through the `<-`operator. A vector can have more than 1 object.

Use `alt`+ `-` (Windows) or `option`+ `-`(Mac) for the `<-` operator.


```r
x <- 1
y <- FILL_THIS_IN #store multiple values of 1 type
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

However, a vector contains only 1 type of data. So if you tried this. What do you think would happen?


```r
z <- FILL_THIS_IN
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

```r
z
```

```
## Error in eval(expr, envir, enclos): object 'z' not found
```

It coerces the 1 into a character vector.

Vectors are 1 dimensional and you can look at various properties of a vector like length.


```r
FILL_THIS_IN(y)
```

```
## Error in FILL_THIS_IN(y): could not find function "FILL_THIS_IN"
```

To get the second element in a vector you use `[]`


```r
FILL_THIS_IN
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

## Matrix

Multiple objects are stored in a matrix. Like a vector, a matrix only contains 1 type of data, but it has more than 1 dimension.

Matrix is a common data object in many types of bioinformatic analyses.


```r
matx <- FILL_THIS_IN(data=1:9,nrow=3,ncol=3)
```

```
## Error in FILL_THIS_IN(data = 1:9, nrow = 3, ncol = 3): could not find function "FILL_THIS_IN"
```

```r
matx
```

```
## Error in eval(expr, envir, enclos): object 'matx' not found
```

You can also create a vector like this:


```r
mat2 <- FILL_THIS_IN(y,z)
```

```
## Error in FILL_THIS_IN(y, z): could not find function "FILL_THIS_IN"
```

```r
mat2
```

```
## Error in eval(expr, envir, enclos): object 'mat2' not found
```

```r
class(mat2)
```

```
## Error in eval(expr, envir, enclos): object 'mat2' not found
```

Use [row,column] to access elements of a matrix


```r
matx[FILL_THIS_IN] # Access the 3rd element of the first row
```

```
## Error in eval(expr, envir, enclos): object 'matx' not found
```

```r
matx[FILL_THIS_IN] # Access the first row
```

```
## Error in eval(expr, envir, enclos): object 'matx' not found
```

```r
matx[FILL_THIS_IN] # access the first column
```

```
## Error in eval(expr, envir, enclos): object 'matx' not found
```

You can even name the rows and columns of a matrix.


```r
FILL_THIS_IN(matx) <- c("Earth","Venus","Mars") #name rows
```

```
## Error in FILL_THIS_IN(matx) <- c("Earth", "Venus", "Mars"): object 'matx' not found
```

```r
FILL_THIS_IN(matx) <- c("A","B","C") # name columns
```

```
## Error in FILL_THIS_IN(matx) <- c("A", "B", "C"): object 'matx' not found
```

```r
matx
```

```
## Error in eval(expr, envir, enclos): object 'matx' not found
```

## Data frames

A data.frame is basically just a table. It has a certain number of rows, and a certain number of columns. It's a special type of data object and various operations can be performed on data frames.

"trees" is a built-in dataset in R available as a `data.frame`.


```r
trees
```

```
##    Girth Height Volume
## 1    8.3     70   10.3
## 2    8.6     65   10.3
## 3    8.8     63   10.2
## 4   10.5     72   16.4
## 5   10.7     81   18.8
## 6   10.8     83   19.7
## 7   11.0     66   15.6
## 8   11.0     75   18.2
## 9   11.1     80   22.6
## 10  11.2     75   19.9
## 11  11.3     79   24.2
## 12  11.4     76   21.0
## 13  11.4     76   21.4
## 14  11.7     69   21.3
## 15  12.0     75   19.1
## 16  12.9     74   22.2
## 17  12.9     85   33.8
## 18  13.3     86   27.4
## 19  13.7     71   25.7
## 20  13.8     64   24.9
## 21  14.0     78   34.5
## 22  14.2     80   31.7
## 23  14.5     74   36.3
## 24  16.0     72   38.3
## 25  16.3     77   42.6
## 26  17.3     81   55.4
## 27  17.5     82   55.7
## 28  17.9     80   58.3
## 29  18.0     80   51.5
## 30  18.0     80   51.0
## 31  20.6     87   77.0
```

The columns of the trees `data.frame` object are individual `vector` objects. So trees has 3 columns/vectors that are each 31 elements long. The dbl is just a type of numeric class of data.

Another Example of a data.frame. The ToothGrowth dataset looking at hamster teeth grown with different supplements and doses of Vitamin C.


```r
ToothGrowth
```

```
##     len supp dose
## 1   4.2   VC  0.5
## 2  11.5   VC  0.5
## 3   7.3   VC  0.5
## 4   5.8   VC  0.5
## 5   6.4   VC  0.5
## 6  10.0   VC  0.5
## 7  11.2   VC  0.5
## 8  11.2   VC  0.5
## 9   5.2   VC  0.5
## 10  7.0   VC  0.5
## 11 16.5   VC  1.0
## 12 16.5   VC  1.0
## 13 15.2   VC  1.0
## 14 17.3   VC  1.0
## 15 22.5   VC  1.0
## 16 17.3   VC  1.0
## 17 13.6   VC  1.0
## 18 14.5   VC  1.0
## 19 18.8   VC  1.0
## 20 15.5   VC  1.0
## 21 23.6   VC  2.0
## 22 18.5   VC  2.0
## 23 33.9   VC  2.0
## 24 25.5   VC  2.0
## 25 26.4   VC  2.0
## 26 32.5   VC  2.0
## 27 26.7   VC  2.0
## 28 21.5   VC  2.0
## 29 23.3   VC  2.0
## 30 29.5   VC  2.0
## 31 15.2   OJ  0.5
## 32 21.5   OJ  0.5
## 33 17.6   OJ  0.5
## 34  9.7   OJ  0.5
## 35 14.5   OJ  0.5
## 36 10.0   OJ  0.5
## 37  8.2   OJ  0.5
## 38  9.4   OJ  0.5
## 39 16.5   OJ  0.5
## 40  9.7   OJ  0.5
## 41 19.7   OJ  1.0
## 42 23.3   OJ  1.0
## 43 23.6   OJ  1.0
## 44 26.4   OJ  1.0
## 45 20.0   OJ  1.0
## 46 25.2   OJ  1.0
## 47 25.8   OJ  1.0
## 48 21.2   OJ  1.0
## 49 14.5   OJ  1.0
## 50 27.3   OJ  1.0
## 51 25.5   OJ  2.0
## 52 26.4   OJ  2.0
## 53 22.4   OJ  2.0
## 54 24.5   OJ  2.0
## 55 24.8   OJ  2.0
## 56 30.9   OJ  2.0
## 57 26.4   OJ  2.0
## 58 27.3   OJ  2.0
## 59 29.4   OJ  2.0
## 60 23.0   OJ  2.0
```

Here the len is a factor which is a special data type that stores the character vector as a special object behind the scenes.

Data Frames, unlike a matrix, can contain many different types of data like dates, characters, numbers.

You can create a dataframe like this.


```r
FILL_THIS_IN("A"=1:2,B=c("A","B"))
```

```
## Error in FILL_THIS_IN(A = 1:2, B = c("A", "B")): could not find function "FILL_THIS_IN"
```

### Some basic functions to help understand your `data.frame` objects are:


```r
# number of rows
FILL_THIS_IN(trees)
```

```
## Error in FILL_THIS_IN(trees): could not find function "FILL_THIS_IN"
```

```r
# number of columns
FILL_THIS_IN(trees)
```

```
## Error in FILL_THIS_IN(trees): could not find function "FILL_THIS_IN"
```

```r
# row x columns
FILL_THIS_IN(trees)
```

```
## Error in FILL_THIS_IN(trees): could not find function "FILL_THIS_IN"
```

```r
# some basic info on the "structure" of the data.frame
FILL_THIS_IN(trees)
```

```
## Error in FILL_THIS_IN(trees): could not find function "FILL_THIS_IN"
```

```r
# calculates some summary statistics on each column
FILL_THIS_IN(trees)
```

```
## Error in FILL_THIS_IN(trees): could not find function "FILL_THIS_IN"
```

```r
# print first 6 rows
FILL_THIS_IN(trees)
```

```
## Error in FILL_THIS_IN(trees): could not find function "FILL_THIS_IN"
```

```r
# print last 6 rows
FILL_THIS_IN(trees)
```

```
## Error in FILL_THIS_IN(trees): could not find function "FILL_THIS_IN"
```

```r
## What type of data is trees?
FILL_THIS_IN(trees) 
```

```
## Error in FILL_THIS_IN(trees): could not find function "FILL_THIS_IN"
```

In base R (without additional packages), we can subset the dataframe, similar to how we subset a matrix.


```r
treesFILL_THIS_IN # gets the first row
```

```
## Error in eval(expr, envir, enclos): object 'treesFILL_THIS_IN' not found
```


```r
treesFILL_THIS_IN ## gets the value of the first column and the first row
```

```
## Error in eval(expr, envir, enclos): object 'treesFILL_THIS_IN' not found
```

```r
treesFILL_THIS_IN # first column, returns a dataframe
```

```
## Error in eval(expr, envir, enclos): object 'treesFILL_THIS_IN' not found
```

However we can also call the named column using `$`. For example if we wanted the Height column. This will drop the name and return a numeric vector.


```r
treesFILL_THIS_IN
```

```
## Error in eval(expr, envir, enclos): object 'treesFILL_THIS_IN' not found
```

```r
FILL_THIS_IN(treesFILL_THIS_IN) # checks the class of the height column
```

```
## Error in FILL_THIS_IN(treesFILL_THIS_IN): could not find function "FILL_THIS_IN"
```

These differences in subsetting return different objects so think about what output you want.

## Basic operations in R

See knitted html for pretty tables.

**Arithmetic** operators allow us to carry out mathematical operations:

| Operator | Description                       |
|----------|:----------------------------------|
| \+       | Add                               |
| \-       | Subtract                          |
| \*       | Multiply                          |
| /        | Divide                            |
| \^       | Exponent                          |
| %%       | Modulus (remainder from division) |

**Relational** operators allow us to compare values:

| Operator | Description              |
|----------|:-------------------------|
| \<       | Less than                |
| \>       | Greater than             |
| \<=      | Less than or equal to    |
| \>=      | Greater than or equal to |
| ==       | Equal to                 |
| !=       | Not equal to             |

-   Arithmetic and relational operators work on vectors.

**Logical** operators allow us to carry out boolean operations:

| Operator | Description        |
|----------|:-------------------|
| !        | Not                |
| \|       | Or (element_wise)  |
| &        | And (element-wise) |
| \|\|     | Or                 |
| &&       | And                |

The vector `a` is created for you using the values 1,2,3. Create a second vector `b` with the values 4,6,8


```r
a <- c(1,2,3)
FILL_THIS_IN
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

Add and subtract the 2 vectors. Try another arithmetic operation from the list above.


```r
FILL_THIS_IN
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

```r
FILL_THIS_IN
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

How would you check if 5 is greater than 7? How would you check if 5+2 is the same as 2+5


```r
FILL_THIS_IN
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

```r
FILL_THIS_IN
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

Let's bind a and b into a matrix called c.


```r
c <- FILL_THIS_IN
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

How would you do the following


```r
FILL_THIS_IN ## select elements greater than 3
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

```r
FILL_THIS_IN ## select elements greater than 3 or equal to 1 
```

```
## Error in eval(expr, envir, enclos): object 'FILL_THIS_IN' not found
```

## Where to get help?

R like any language can be confusing at times. It's okay if you get stuck.

If you are confused about how to do something or what to do next follow these steps below:

1.  Read the error message (if there is one). Error messages often times help convey what you might have missed.
2.  Check your code for simple mistakes. Did you miss a bracket or quotation mark, did you misspell an object name or use `=` instead of `==`?
3.  Read the function documentation. Use the `?` command to pull up the help page.

-   Check the inputs the function needs (a `data.frame` vs a `matrix`)

4.  Copy and paste the error message and name of function into **Google**

### Importantly for Point 4, always accredit the code you use

If you used stackoverflow or any other website use code comments like \# or a comment before the code chunk to accredit the webite

Ex.

Code from www.helpfulwebsite.fakename.com/user1/howto


```r
1+1 #www.helpfulwebsite.fakename.com/user1/howto
```

```
## [1] 2
```

# Introduction to RNAseq data analysis

## Accreditation

The BiocSwirl interactive course was based on [this RNA-seq workflow](https://master.bioconductor.org/packages/release/workflows/vignettes/rnaseqGene/inst/doc/rnaseqGene.html) published by Love et al., updated in 2019.

## Overall Learning outcomes

-   What is RNAseq?
-   Some considerations for planning RNAseq experiments
-   What kind of questions can be addressed using RNAseq?
-   What is differential expression analysis?
-   How to conduct differential expression analysis of RNAseq data in R

## Resources mentioned in the lecture

-   A short overview over [gene expression](https://www.nature.com/scitable/topicpage/gene-expression-14121669/) published by Scitable (Nature)
-   [RNA-Seq: a revolutionary tool for transcriptomics, Wang et al. 2009](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2949280/)
-   An overview over [different RNAseq analysis workflows](https://www.cd-genomics.com/resourse-Bioinformatics-Workflow-of-RNA-Seq.html)
-   [The RNA-seq workflow used in this class for differential expression analysis](https://master.bioconductor.org/packages/release/workflows/vignettes/rnaseqGene/inst/doc/rnaseqGene.html) published by Love et al., updated in 2019.
-   The [BiocSwirl](https://github.com/biocswirl-dev-team/BiocSwirl) documentation on github


## RNAseq workflow and course structure

![RNAseq workflow image](https://raw.githubusercontent.com/biocswirl-dev-team/learning_resources/workshop_cshl/CSHL_workshop/RNAseq.jpg)

### Steps of the workflow

Feel free to take notes on the different steps as you work your way through the RNAseq workflow course.

-   Installation of packages:
-   Intro to the biology of RNAseq:
-   fastq download:
-   fastq trimming:
-   Read alignment & quantification:
-   Pre-processing:
-   Principle Component Analysis:
-   DESeq2
-   Examine DESeq2 results:
-   Pathway analysis:
-   FastQC: 

### Tools used within the workflow

Below is a list of tools that are used within the workflow. If available, each tool will be a link to further resources. Feel free to take notes on what you're learning about each tool.

-   [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/):
-   [trimgalore](https://www.bioinformatics.babraham.ac.uk/projects/trim_galore/):
-   [STAR](https://github.com/alexdobin/STAR):
-   [Bowtie2](http://bowtie-bio.sourceforge.net/bowtie2/index.shtml):
-   [Tophat](https://ccb.jhu.edu/software/tophat/index.shtml):
-   [Salmon](https://salmon.readthedocs.io/en/latest/salmon.html):
-   [Bioconductor package Rsubread](https://bioconductor.org/packages/release/bioc/html/Rsubread.html):
-   [Bioconductor package DESeq2](https://bioconductor.org/packages/release/bioc/html/DESeq2.html):
-   [EnrichR](https://maayanlab.cloud/Enrichr/):

## Introduction to Bioconductor

[Bioconductor](https://bioconductor.org/) is an open source collection of bioinformatics software, written in R.

## Introduction to BiocSwirl

[BiocSwirl](https://github.com/biocswirl-dev-team/BiocSwirl) is an R package containing interactive coding courses teaching Bioconductor tools and workflows.

## BiocSwirl course installation


```r
# installation of devtools
install.packages("devtools")
library(devtools)
# installation of biocswirl with vignettes
devtools::install_github("biocswirl-dev-team/BiocSwirl", build_vignettes = TRUE)
# load Biocswirl library
library(BiocSwirl)
# load swirl
library(swirl)
```


```r
# list all available courses
list_courses()
# select the RNAseq course for installation
load_course('RNAseq')
# start the BiocSwirl course environment
start_course()
```

These following commands can be used within the BiocSwirl course environment.


```r
bye() #exits the course environment
play() #suspends feedback, allows you to ‘play’ with code
nxt() #continue feedback
skip() # skips question, not recommended
```

# Stay in touch

-   Visit BiocSwirl's Twitter page for more updates on our project.: <https://twitter.com/bioctools>
-   <https://bioinformaticstutorials.github.io/>
-   <https://github.com/biocswirl-dev-team/BiocSwirl>
