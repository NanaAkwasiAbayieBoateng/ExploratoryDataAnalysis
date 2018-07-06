Exploratory Data Analysis
================
Nana Boateng
July 06, 2018

## Load Required Packages

``` r
#install.packages("pacman")
library(pacman)

pacman::p_load(tidyverse,janitor,DataExplorer,skimr)
```

The ISLR package created to store the data for Introduction to
Statistical Learning with Applications in R(Gareth James, Daniela
Witten, Trevor Hastie and Rob Tibshirani)

The dataset can be found
[here](%22https://www.machinelearningplus.com/machine-learning/caret-package/#63preparethetestdatasetandpredict%22)

[here](http://rmarkdown.rstudio.com)

For this tutorial, I am going to use a modified version of the Orange
Juice Data, originally made available in the ISLR package.

The goal of this dataset is to predict which of the two brands of orange
juices did the customers buy.

The predictor variables are characteristics of the customer and the
product itself. It contains 1070 rows with 18 columns. The response
variable is ‘Purchase’ which takes either the value ‘CH’(citrus hill) or
‘MM’(minute maid).

``` r
# Import dataset
orangejuice<-read_csv('https://raw.githubusercontent.com/selva86/datasets/master/orange_juice_withmissing.csv')
```

    ## Parsed with column specification:
    ## cols(
    ##   Purchase = col_character(),
    ##   WeekofPurchase = col_integer(),
    ##   StoreID = col_integer(),
    ##   PriceCH = col_double(),
    ##   PriceMM = col_double(),
    ##   DiscCH = col_double(),
    ##   DiscMM = col_double(),
    ##   SpecialCH = col_integer(),
    ##   SpecialMM = col_integer(),
    ##   LoyalCH = col_double(),
    ##   SalePriceMM = col_double(),
    ##   SalePriceCH = col_double(),
    ##   PriceDiff = col_double(),
    ##   Store7 = col_character(),
    ##   PctDiscMM = col_double(),
    ##   PctDiscCH = col_double(),
    ##   ListPriceDiff = col_double(),
    ##   STORE = col_integer()
    ## )

``` r
orangejuice
```

    ## # A tibble: 1,070 x 18
    ##    Purchase WeekofPurchase StoreID PriceCH PriceMM DiscCH DiscMM SpecialCH
    ##    <chr>             <int>   <int>   <dbl>   <dbl>  <dbl>  <dbl>     <int>
    ##  1 CH                  237       1    1.75    1.99   0       0           0
    ##  2 CH                  239       1    1.75    1.99   0       0.3         0
    ##  3 CH                  245       1    1.86    2.09   0.17    0           0
    ##  4 MM                  227       1    1.69    1.69   0       0           0
    ##  5 CH                  228       7    1.69    1.69   0       0           0
    ##  6 CH                  230       7    1.69    1.99   0       0           0
    ##  7 CH                  232       7    1.69    1.99   0       0.4         1
    ##  8 CH                  234       7    1.75    1.99   0       0.4         1
    ##  9 CH                  235       7    1.75    1.99   0       0.4         0
    ## 10 CH                  238       7    1.75    1.99   0       0.4         0
    ## # ... with 1,060 more rows, and 10 more variables: SpecialMM <int>,
    ## #   LoyalCH <dbl>, SalePriceMM <dbl>, SalePriceCH <dbl>, PriceDiff <dbl>,
    ## #   Store7 <chr>, PctDiscMM <dbl>, PctDiscCH <dbl>, ListPriceDiff <dbl>,
    ## #   STORE <int>

``` r
write_csv(orangejuice,"/Users/nanaakwasiabayieboateng/Documents/memphisclassesbooks/DataMiningscience/orangejuice.csv")

#ExploratoryDataAnalysis
```
