
## Casefold 

**Definition:** Translate character to lower or upper case.

**Example:** Our characters are transformed to lower case if we specify upper = FALSE (default option) within the casefold function…

<code> casefold(x, upper = FALSE)               # Convert to lower case letters </code>

<code> #"example" </code>

…or to upper case if we specify upper = TRUE:

<code> casefold(x, upper = TRUE)                 # Convert to upper case letters </code>


<code> *#"EXAMPLE"* </code>

##  Cut

**Definition:** The cut R function converts numeric values into factorial ranges.

**Basic R Syntax:** <code> cut(my_values, my_breaks)              # Basic R syntax of cut function </code>

**Example:**

<code> x <- 1:10        # Create example vector </code>

<code> x                                              # Print example vector </code>

<code>  #1  2  3  4  5  6  7  8  9 10 </code>

The previous output of the RStudio console shows that our example data is a simple numeric vector ranging from 1 to 10.

## Dbinom – 

**Definition:** Return corresponding value of binomial density.

**Example:**

apply the pbinom function to create a plot of the binomial cumulative distribution function (CDF) in R. First, we need to create an input vector.

<code> x_pbinom <- seq(0, 100, by = 1)                       # Specify x-values for pbinom function </code>

Now, we can apply the pbinom command…

<code>  y_pbinom <- pbinom(x_pbinom, size = 100, prob = 0.5)  # Apply pbinom function </code>
  
…and draw a plot of the binomial CDF:

<code> plot(y_pbinom)                                        # Plot pbinom values </code>
![a](https://statisticsglobe.com/wp-content/uploads/2019/08/figure-2-binom-distribution-function-plot-in-r.png)

