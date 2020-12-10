# 20 Functions in R 

## Casefold 

**Function 1 Casefold**

**Definition:** Translate character to lower or upper case.

**Example:** Our characters are transformed to lower case if we specify upper = FALSE (default option) within the casefold function…

<code> casefold(x, upper = FALSE)               # Convert to lower case letters </code>

<code> #"example" </code>

…or to upper case if we specify upper = TRUE:

<code> casefold(x, upper = TRUE)                 # Convert to upper case letters </code>


<code> *#"EXAMPLE"* </code>

##  Cut

**Function 2 Cut**

**Definition:** The cut R function converts numeric values into factorial ranges.

**Basic R Syntax:** <code> cut(my_values, my_breaks)              # Basic R syntax of cut function </code>

**Example:**

<code> x <- 1:10        # Create example vector </code>

<code> x                                              # Print example vector </code>

<code>  #1  2  3  4  5  6  7  8  9 10 </code>

The previous output of the RStudio console shows that our example data is a simple numeric vector ranging from 1 to 10.

## Dbinom 

**Function 3 Dbinom**

**Definition:** Return corresponding value of binomial density.

**Example:**

apply the pbinom function to create a plot of the binomial cumulative distribution function (CDF) in R. First, we need to create an input vector.

<code> x_pbinom <- seq(0, 100, by = 1)                       # Specify x-values for pbinom function </code>

Now, we can apply the pbinom command…

<code>  y_pbinom <- pbinom(x_pbinom, size = 100, prob = 0.5)  # Apply pbinom function </code>
  
…and draw a plot of the binomial CDF:

<code> plot(y_pbinom)                                        # Plot pbinom values </code>
![a](https://statisticsglobe.com/wp-content/uploads/2019/08/figure-2-binom-distribution-function-plot-in-r.png)

## Dt 

**Function 4 dt**

**Definition:** Return corresponding value of Student t PDF.

**Example(Student t Probability Density Function)**

First, we need to create a vector of quantiles in R:

<code>x_dt <- seq(- 10, 10, by = 0.01)                    # Specify x-values for dt function </code>

After running the previous R code, we can apply the dt command in R as follows. In the example, we use 3 degrees of freedom (as specified by the argument df = 3):

<code>y_dt <- dt(x_dt, df = 3)                            # Apply dt function </code>
  
The Student t density values are now stored in the data object y_dt. We can draw a graph representing these values with the plot R function:

<code>plot(y_dt)                                          # Plot dt values </code>
![a1](https://statisticsglobe.com/wp-content/uploads/2019/09/figure-1-r-command-dt-density-plot.png)

## Exists 

**Function 5 Exists**

**Definition:** Check whether an object is defined in the R environment.

**Basic R Syntax:***
<code>exists(x) </code>

**Example: (Apply exists() Function to Vector)**

Let’s create a simple vector for our first example:

<code> x <- c(2, 9, 5, 3)                        # Create example vector </code>
  
 And not let’s use exists() to check if this vector is properly defined in our R environment:
 
 <code> exists("x")                               # Apply exists function to vector
  
#TRUE </code>

The exists function returns TRUE to the RStudio console. In other words: Yes, the vector x exists.

For comparison, let’s also apply the exists function to a vector that we did not define before:

<code> exists("y")                               # Apply exists function to non-existent vector
  
#FALSE </code>

## Format

**Function 6 Format**

The format R function encodes data objects into common formats.

**Example:**

<code> format(values)                # Basic R syntax of format function </code>

<code> set.seed(243266)              # Set seed </code>

<code>  x <- rnorm(5)                 # Random values </code>

<code>  x                             # Print example vector </code>

<code> #  -1.5894026 -0.9007914  0.8997223 -0.4310145  1.5865680 </code>

It shows that the example data is a numeric vector containing five vector elements.

## Geometric Mean

**Function 7 Geometric Mean**

Compute the geometric mean

**Example:**

We can calculate the geometric mean based on these R functions as follows:

<code>exp(mean(log(x)))                  # Compute geometric mean manually </code>
  
<code> # 4.209156 </code>

the geometric mean of our example data is 4.209156.

## Heatmap

**Function 8 Heatmap**

Create heatmap in Base R.

**Example:**

<code> set.seed(123)                                                     # Set seed for reproducibility </code>

<code> data <- matrix(rnorm(100, 0, 10), nrow = 10, ncol = 10)           # Create example data </code>
  
<code> colnames(data) <- paste0("col", 1:10)                             # Column names  </code>
  
<code> rownames(data) <- paste0("row", 1:10) </code>
  
  Our data contains ten columns and ten rows with normally distributed random values.
  
  <code> heatmap(data)                                                     # Apply heatmap function </code>
  
  ![a3](https://statisticsglobe.com/wp-content/uploads/2019/10/figure-1-heatmap-function-base-r.png)
  
   illustrates the output of the previous R code. By default, the heatmap function returns a heatmap with column and row names as well as a dendogram.
   
## Length

**Function 9 Lenght(x)**

Return the length of data objects such as vectors or lists.

**Example:**

we need to create a vector or array in R:

<code> x <- c(8, 17, 23, 93, - 20, 15, 13, 55, 29, - 84)  # Example vector in R </code>

Now, we can apply the length R command to this vector:

<code>length(x)                                          # Apply length function  </code>

<code> # 10 </code>

The length function returns the value 10 to the RStudio console – The length of our vector is 10.

## nchar(x)

**Function 10 nchar(x)**

Count the number of characters in a string


Declaring a **string** to work with

<code> word <- "Language"						</code>


Applying the **nchar** function

<code> nchar(word)								</code>

**Result 8**


## nrow(df)

**Function 11 nrow(df)**

Shows the number of rows in the data frame


An example of a data frame, where x are the rows and y the columns

<code> df <- data.frame(x = 1:3, y = c('a', 'b', 'c'))  </code>


Applying the function **nrow** to a data frame 

<code> nrow(df) 										</code>


## ncol(df)

**Function 12 ncol(df)**

Shows the number of columns of a data frame


Applying the function **ncol** to a data frame

<code> ncol(df)								 </code>


## dim(df)

**Function 13 dim(df)**

Shows the number of rows and columns of a data frame
  

Applying the function **dim** to a data frame

<code> dim(df) </code>


## View(df)

**Function 14 View(df)**

Shows the data frame table in a window


Applying the function **View** to a data frame

<code> View(df)  </code>


## hist(z)

**Function 15 hist(z)**

Creates an histogram of a vector


Declaring the vector

<code> z <- c(1, 1, 2, 2, 3, 4, 4, 5, 6, 6)</code>


Applying the **hist** function to a vector 

<code> hist(z)</code>


## quantile(z)

**Function 16 plot(x)**

Get Quantile Percentages of a vector


Applying the quantile function to a vector

<code> quantile(z) </code>


## plot(x)

**Function 17**

Plots the data of a data frame


Applying the function to a data frame

<code> plot(df) </code>


## mean(x)

**Function 18 mean(X)**

Get the mean of a vector


Applying the mean function to a vector

<code> mean(z)</code>


## median(x)

**Function 19 median(x)**

Gets the median of a vector


Applying the median function to a vector

<code> median(z) </code>


## rm()

**Function 20 rm(list = ls())**

Removes all the variables in the environment


Applying the rm function to our environment

<code> rm(list = ls()) </code>
