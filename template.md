Simple document
================
Xieyu

I’m an R Markdown document!

# Section0: libraries

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.2.1     ✔ readr     2.2.0
    ## ✔ forcats   1.0.1     ✔ stringr   1.6.0
    ## ✔ ggplot2   4.0.3     ✔ tibble    3.3.1
    ## ✔ lubridate 1.9.5     ✔ tidyr     1.3.2
    ## ✔ purrr     1.2.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

# Section 1

Here’s a **code chunk** that samples from a *normal distribution*:

``` r
samp = rnorm(100)
length(samp)
```

    ## [1] 100

# Section 2

I can take the mean of the sample, too! The mean is -0.0449265. \#click
Knit

# section 3: a tibble

``` r
plot_df=
  tibble(
    x=rnorm(1000, sd=0.5),
    y=1+2*x+rnorm(1000)
  )
head(plot_df)
```

    ## # A tibble: 6 × 2
    ##         x     y
    ##     <dbl> <dbl>
    ## 1 -0.0184 0.134
    ## 2  0.830  2.00 
    ## 3 -0.406  1.75 
    ## 4 -0.0606 1.87 
    ## 5 -0.359  0.400
    ## 6  0.781  2.11

# Section 4:plots

    ## `stat_bin()` using `bins = 30`. Pick better value `binwidth`.

![](template_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->![](template_files/figure-gfm/unnamed-chunk-4-2.png)<!-- -->

# Section5: Learning Assessment2

Write a named code chunk that creates a dataframe comprised of: a
numeric variable containing a random sample of size 500 from a normal
variable with mean 1; a logical vector indicating whether each sampled
value is greater than zero; and a numeric vector containing the absolute
value of each element. Then, produce a histogram of the absolute value
variable just created. Add an inline summary giving the median value
rounded to two decimal places. What happens if you set eval = FALSE to
the code chunk? What about echo = FALSE?

This plot shows the distribution of the absolute value of
$X \sim N(1,1)$.

``` r
# click setting on the right, 
set.seed(0)

la_df= tibble(
  num_var= rnorm(500, mean=1),
  log_var= num_var > 0, # either T or F
  abs_var= abs(num_var) #abs() absolute value
)
ggplot(la_df, aes(x = abs_var))+geom_histogram()
```

    ## `stat_bin()` using `bins = 30`. Pick better value `binwidth`.

![](template_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

what if I try to add a histogram

``` r
ggplot(plot_df, aes(x=x)) + geom_histogram()
```

    ## `stat_bin()` using `bins = 30`. Pick better value `binwidth`.

![](template_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

The median is 0.94

# Section6 : Formating

## Text formatting

*italic* or *italic* **bold** or **bold** `code` `num_var`
superscript<sup>2</sup> and subscript<sub>2</sub>

## Headings

# 1st Level Header

## 2nd Level Header

### 3rd Level Header

## Lists

- Bulleted list item 1

- Item 2

  - Item 2a

  - Item 2b

1.  Numbered list item 1

2.  Item 2. The numbers are incremented automatically in the output.

## Tables

| First Header | Second Header |
|--------------|---------------|
| Content Cell | Content Cell  |
| Content Cell | Content Cell  |

# Section3: Learning Assessment3

After the previous code chunk, write a bullet list given the mean,
median, and standard deviation of the original random sample.

- The median is 0.94

- The mean is 1

- The standard deviation is 0.99
