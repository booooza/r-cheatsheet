# Basic Commands

## Hello World

``` r
print("Hello World")
```

    ## [1] "Hello World"

## Get help for a command

``` r
?load
```

## Calculations

R performs addition, subtraction, multiplication, and division with +,
-, \*, and /

``` r
25 * 4 + 9 / 3
```

    ## [1] 103

## Comments

R interprets anything after a \# as a comment.

``` r
persnickety_count <- 0
```

## Data Types

-   Numeric: Any number with or without a decimal point: 23, 0.03and the
    numeric null value NA.
-   Character: Any grouping of characters on your keyboard (letters,
    numbers, spaces, symbols, etc.) or text. Most strings are surrounded
    by single quotes: ’ … ’ or double quotes " … “, though we prefer
    single quotes. Sometimes you will hear this type referred to
    as”string."
-   Logical: This data type only has two possible values— either TRUE or
    FALSE (without quotes). It’s helpful to think of logical types or
    booleans as on and off switches or as the answers to a “yes” or “no”
    question.
-   Vectors: A list of related data that is all the same type.
-   NA: This data type represents the absence of a value, and is
    represented by the keyword NA (without quotes) but it has its own
    significance in the context of the different types. That is there is
    a numeric NA, a character NA, and a logical NA.

``` r
class(2)        # numeric
```

    ## [1] "numeric"

``` r
class('hello')  # character
```

    ## [1] "character"

``` r
class('23')     # character
```

    ## [1] "character"

``` r
class (FALSE)   # logical
```

    ## [1] "logical"

``` r
class(NA)       # logical
```

    ## [1] "logical"

## Variables

``` r
# Greeting
message_string <- "Hello there"
print(message_string)
```

    ## [1] "Hello there"

``` r
# Farewell
message_string <- "Hasta la vista"
print(message_string)
```

    ## [1] "Hasta la vista"

## Vectors

In R, vectors are a list-like structure that contain items of the same
data type.

``` r
phone <- c(123, 456, 789)
print(phone)
```

    ## [1] 123 456 789

``` r
typeof(phone)
```

    ## [1] "double"

``` r
print(phone[1])   # R starts to count at 1
```

    ## [1] 123

## Conditionals

``` r
if (TRUE) {
   print("Go to sleep!")
} else {
   print("Wake up!")
}
```

    ## [1] "Go to sleep!"

### ifelse() function

This function takes a logical expression test on some vector, if the
test is True, the first action True is taken otherwise the second action
False is taken. 

``` r
# ifelse() function
score <- c(77,35,89,100,45,67,50)
ifelse(score >= 50, "Pass", "Fail")
```

    ## [1] "Pass" "Fail" "Pass" "Pass" "Fail" "Pass" "Pass"

## Comparison Operators

-   Less than: `<`

-   Greater than: `>`

-   Less than or equal to: `<=`

-   Greater than or equal to: `>=`

-   Is equal to: `==`

-   Is NOT equal to: `!=`

``` r
10 < 12 # Evaluates to TRUE
```

    ## [1] TRUE

## Logical Operators

-   the AND operator (`&`)

-   the OR operator (`|`)

-   the NOT operator, otherwise known as the bang operator (`!`)

``` r
stopLight <- 'green'
pedestrians <- 0
if (stopLight == 'green' & pedestrians == 0) {
  print('Go!');
} else {
  print('Stop');
}
```

    ## [1] "Go!"

## Calling a Function

``` r
sort(c(2,4,10,5,1)); # Outputs c(1,2,4,5,10)
```

    ## [1]  1  2  4  5 10

``` r
length(c(2,4,10,5,1)); # Outputs 5
```

    ## [1] 5

``` r
sum(5,15,10) #Outputs 30
```

    ## [1] 30

``` r
data <- c(120,22,22,31,15,120)

unique_vals <- unique(data)
print(unique_vals)
```

    ## [1] 120  22  31  15

``` r
solution <- sqrt(49)
print(solution)
```

    ## [1] 7

``` r
round_down <- floor(3.14)
print(round_down)
```

    ## [1] 3

``` r
round_up <- ceiling(3.14)
print(round_up)
```

    ## [1] 4

## Loops

### For-Loop

``` r
for ( x in 1:5){
    print(x)
}
```

    ## [1] 1
    ## [1] 2
    ## [1] 3
    ## [1] 4
    ## [1] 5

### While-Loop

``` r
x  <-  10
while ( x >= 5 ) {
     print (x)
     x  <-  x-1
}
```

    ## [1] 10
    ## [1] 9
    ## [1] 8
    ## [1] 7
    ## [1] 6
    ## [1] 5

### Repeat-Loop

``` r
counter <- 10

repeat { 
    print(counter)
    counter <- counter - 1
    if (counter < 5)
        break
}
```

    ## [1] 10
    ## [1] 9
    ## [1] 8
    ## [1] 7
    ## [1] 6
    ## [1] 5

## Recursion

``` r
factorial <- function(n) {
    if (n == 0)     
        return (1)

    else 
        return (n * factorial (n-1))
}

factorial(5)
```

    ## [1] 120

## Importing Packages

Base R refers the R language by itself and all that it can do without
importing any packages.

[CRAN](https://cran.r-project.org/) offers more packages to extend the
functionality of R. Dplyr is a package used to clean, process, and
organize data which you will use as you learn about R. The goal of
‘readr’ is to provide a fast and friendly way to read rectangular data
(like ‘csv’, ‘tsv’, and ‘fwf’).

``` r
# load libraries
library('dplyr')
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
library('readr')
```

## CSV Import options

``` r
data <- read.csv('data/biostats.csv')
# data <- read.csv(file.choose())
data <- read.csv("https://people.sc.fsu.edu/~jburkardt/data/csv/biostats.csv")
```

### readr

``` r
# load data frame
biostats <- read_csv('data/biostats.csv')
```

    ## 
    ## ── Column specification ────────────────────────────────────────────────────────
    ## cols(
    ##   Name = col_character(),
    ##   Sex = col_character(),
    ##   Age = col_double(),
    ##   `Height (in)` = col_double(),
    ##   `Weight (lbs)` = col_double()
    ## )

``` r
# inspect data frame
biostats
```

    ## # A tibble: 18 x 5
    ##    Name  Sex     Age `Height (in)` `Weight (lbs)`
    ##    <chr> <chr> <dbl>         <dbl>          <dbl>
    ##  1 Alex  M        41            74            170
    ##  2 Bert  M        42            68            166
    ##  3 Carl  M        32            70            155
    ##  4 Dave  M        39            72            167
    ##  5 Elly  F        30            66            124
    ##  6 Fran  F        33            66            115
    ##  7 Gwen  F        26            64            121
    ##  8 Hank  M        30            71            158
    ##  9 Ivan  M        53            72            175
    ## 10 Jake  M        32            69            143
    ## 11 Kate  F        47            69            139
    ## 12 Luke  M        34            72            163
    ## 13 Myra  F        23            62             98
    ## 14 Neil  M        36            75            160
    ## 15 Omar  M        38            70            145
    ## 16 Page  F        31            67            135
    ## 17 Quin  M        29            71            176
    ## 18 Ruth  F        28            65            131

``` r
head(biostats)
```

    ## # A tibble: 6 x 5
    ##   Name  Sex     Age `Height (in)` `Weight (lbs)`
    ##   <chr> <chr> <dbl>         <dbl>          <dbl>
    ## 1 Alex  M        41            74            170
    ## 2 Bert  M        42            68            166
    ## 3 Carl  M        32            70            155
    ## 4 Dave  M        39            72            167
    ## 5 Elly  F        30            66            124
    ## 6 Fran  F        33            66            115

``` r
summary(biostats)
```

    ##      Name               Sex                 Age         Height (in)   
    ##  Length:18          Length:18          Min.   :23.00   Min.   :62.00  
    ##  Class :character   Class :character   1st Qu.:30.00   1st Qu.:66.25  
    ##  Mode  :character   Mode  :character   Median :32.50   Median :69.50  
    ##                                        Mean   :34.67   Mean   :69.06  
    ##                                        3rd Qu.:38.75   3rd Qu.:71.75  
    ##                                        Max.   :53.00   Max.   :75.00  
    ##   Weight (lbs)  
    ##  Min.   : 98.0  
    ##  1st Qu.:132.0  
    ##  Median :150.0  
    ##  Mean   :146.7  
    ##  3rd Qu.:165.2  
    ##  Max.   :176.0
