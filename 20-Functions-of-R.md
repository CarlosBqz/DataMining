
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
